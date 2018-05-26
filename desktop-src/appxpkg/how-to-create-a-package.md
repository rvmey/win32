---
title: How to create an app package (C++)
description: Learn how to create an app package for a Windows Store app using the packaging API.
ms.assetid: FD677D75-50D5-4228-891F-73B5F40679B0
ms.date: 05/31/2018
ms.topic: article
ms.author: windowssdkdev
ms.prod: windows
ms.technology: desktop
---

# How to create an app package (C++)

> [!Note]  
> If you're creating a UWP app package, see [Create an app package with the MakeAppx.exe tool](https://aka.ms/package-with-makeappx).

 

Learn how to create an app package for a Windows Store app using the [packaging API](interfaces.md).

If you want to create a desktop app package manually, you can also use the MakeAppx.exe tool which utilizes the [packaging API](interfaces.md). See [App packager (MakeAppx.exe)](make-appx-package--makeappx-exe-.md) for more information.

If you are using Visual Studio, it's recommended that you use the Visual Studio packaging wizard to package your app. For more details, see [Packaging UWP apps](https://aka.ms/packaging-uwp-apps).

## Instructions

### Step 1: Create a package writer

To create a package writer, call the [**IAppxFactory::CreatePackageWriter**](/windows/win32/AppxPackaging/nf-appxpackaging-iappxfactory-createpackagewriter?branch=master) method. The first parameter is an output stream where the package will be written. The second parameter is a pointer to an [**APPX\_PACKAGE\_SETTINGS**](/windows/win32/AppxPackaging/ns-appxpackaging-appx_package_settings?branch=master) structure that specifies package settings. The third parameter is an output parameter that receives a pointer to an [**IAppxPackageWriter**](/windows/win32/AppxPackaging/nn-appxpackaging-iappxpackagewriter?branch=master) pointer.


```C++
#include <windows.h>
#include <shlwapi.h>
#include <AppxPackaging.h>

// We store the produced package under this file name.
const LPCWSTR OutputPackagePath = L"HelloWorld.appx";

int wmain()
{
    HRESULT hr = S_OK;

    // Specify the appropriate COM threading model
    hr = CoInitializeEx(NULL, COINIT_MULTITHREADED);

    if (SUCCEEDED(hr))
    {
        // Create a package writer
        IAppxPackageWriter* packageWriter = NULL;

        hr = GetPackageWriter(OutputPackagePath, &amp;packageWriter);
    }
}

//
// Creates an app package writer with default settings.
//
// Parameters:
//   outputFileName  
//     Fully qualified name of the app package (.appx file) to be created.
//   writer 
//     On success, receives the created instance of IAppxPackageWriter.
//
HRESULT GetPackageWriter(
    _In_ LPCWSTR outputFileName,
    _Outptr_ IAppxPackageWriter** writer)
{
    const LPCWSTR Sha256AlgorithmUri = L"http://www.w3.org/2001/04/xmlenc#sha256"; 
    HRESULT hr = S_OK;
    IStream* outputStream = NULL;
    IUri* hashMethod = NULL;
    APPX_PACKAGE_SETTINGS packageSettings = {0};
    IAppxFactory* appxFactory = NULL;

    // Create a stream over the output file for the package 
    hr = SHCreateStreamOnFileEx(
            outputFileName,
            STGM_CREATE | STGM_WRITE | STGM_SHARE_EXCLUSIVE,
            0,     // default file attributes
            TRUE,  // create file if it does not exist
            NULL,  // no template
            &amp;outputStream);

    // Create default package writer settings, including hash algorithm URI
    // and Zip format.
    if (SUCCEEDED(hr))
    {        hr = CreateUri(
                Sha256AlgorithmUri,
                Uri_CREATE_CANONICALIZE,
                0, // reserved parameter
                &amp;hashMethod);
    }

    if (SUCCEEDED(hr))
    {
        packageSettings.forceZip32 = TRUE;
        packageSettings.hashMethod = hashMethod;
    }

    // Create a new Appx factory
    if (SUCCEEDED(hr))
    {
        hr = CoCreateInstance(
                __uuidof(AppxFactory),
                NULL,
                CLSCTX_INPROC_SERVER,
                __uuidof(IAppxFactory),
                (LPVOID*)(&amp;appxFactory));
    }

    // Create a new package writer using the factory
    if (SUCCEEDED(hr))
    {
        hr = appxFactory->CreatePackageWriter(
                outputStream,
                &amp;packageSettings,
                writer);
    }

    // Clean up allocated resources
    if (appxFactory != NULL)
    {
        appxFactory->Release();
        appxFactory = NULL;
    }
    if (hashMethod != NULL)
    {
        hashMethod->Release();
        hashMethod = NULL;
    }
    if (outputStream != NULL)
    {
        outputStream->Release();
        outputStream = NULL;
    }
    return hr;
}
```



### Step 2: Add the payload files for your app to the package

Call the [**IAppxPackageWriter::AddPayloadFile**](/windows/win32/AppxPackaging/nf-appxpackaging-iappxpackagewriter-addpayloadfile?branch=master) method to add files to the package. The first parameter is the relative path of the file. The second parameter indicates the content type of the file. The third parameter specifies options from the [**APPX\_COMPRESSION\_OPTION**](/windows/win32/AppxPackaging/ne-appxpackaging-appx_compression_option?branch=master) enumeration. The fourth parameter is the input stream for the file.


```C++
// Path where all input files are stored
const LPCWSTR DataPath = L"Data\\";

// Add all payload files to the package writer
for (int i = 0; SUCCEEDED(hr) &amp;&amp; (i < PayloadFilesCount); i++)
{
    IStream* fileStream = NULL;

    hr = GetFileStream(DataPath, PayloadFilesName[i], &amp;fileStream);

    if (SUCCEEDED(hr))
    {
        packageWriter->AddPayloadFile(
            PayloadFilesName[i],
            PayloadFilesContentType[i],
            PayloadFilesCompression[i],
            fileStream);
        }

        if (fileStream != NULL)
        {
            fileStream->Release();
            fileStream = NULL;
        }
    }
}
```



The previous code uses these variable definitions and `GetFileStream` helper function.


```C++
#include <strsafe.h>
#include <shlwapi.h>

// The produced app package's content consists of these files, with
// corresponding content types and compression options.
const int PayloadFilesCount = 4;
const LPCWSTR PayloadFilesName[PayloadFilesCount] = {
    L"AppTile.png",
    L"Default.html",
    L"images\\smiley.jpg",
    L"Error.html",
};
const LPCWSTR PayloadFilesContentType[PayloadFilesCount] = {
    L"image/png",
    L"text/html",
    L"image/jpeg",
    L"text/html",
};
const APPX_COMPRESSION_OPTION PayloadFilesCompression[PayloadFilesCount] = {
    APPX_COMPRESSION_OPTION_NONE,
    APPX_COMPRESSION_OPTION_NORMAL,
    APPX_COMPRESSION_OPTION_NONE,
    APPX_COMPRESSION_OPTION_NORMAL,
};

//
// Creates a readable IStream over the specified file. For simplicity, we assume that the fully 
// qualified file name is 100 characters or less. Your code should 
// handle longer names, and allocate the buffer dynamically.
//
// Parameters:
//   path 
//      Path of the folder that contains the file to be opened; must end with a '\'
//   fileName 
//      Name, of the file to be opened, not including the path
//   stream 
//      On success, receives the created instance of IStream
//
HRESULT GetFileStream(
    _In_ LPCWSTR path,
    _In_ LPCWSTR fileName,
    _Outptr_ IStream** stream)
{
    HRESULT hr = S_OK;
    const int MaxFileNameLength = 100;
    WCHAR fullFileName[MaxFileNameLength + 1];

    // Create full file name by concatenating path and fileName
    hr = StringCchCopyW(fullFileName, MaxFileNameLength, path);
    if (SUCCEEDED(hr))
    {
        hr = StringCchCat(fullFileName, MaxFileNameLength, fileName);
    }

    // Create stream for reading the file
    if (SUCCEEDED(hr))
    {
        hr = SHCreateStreamOnFileEx(
                fullFileName,
                STGM_READ | STGM_SHARE_EXCLUSIVE,
                0,      // default file attributes
                FALSE,  // don't create new file
                NULL,   // no template
                stream);
    }
    return hr;
}
```



### Step 3: Add the package manifest to the package

Every package must have a package manifest. To add the package manifest to the package, create an input stream for the file, then call the [**IAppxPackageWriter::Close**](/windows/win32/AppxPackaging/nf-appxpackaging-iappxpackagewriter-close?branch=master) method to write the manifest at the end of the package and close the output stream for package writer.

This code uses the `GetFileStream` helper function shown in the previous step to create the stream for the package manifest.


```C++
// We read the app package's manifest from this file
const LPCWSTR ManifestFileName = L"AppxManifest.xml";

IStream* manifestStream = NULL;

hr = GetFileStream(DataPath, ManifestFileName, &amp;manifestStream);

if (SUCCEEDED(hr))
{
    hr = packageWriter->Close(manifestStream);
}

if (manifestStream != NULL)
{
    manifestStream->Release();
    manifestStream = NULL;
}
```



### Step 4: Clean up the package writer

Before returning from the `wmain` function, call the [**Release**](https://msdn.microsoft.com/library/windows/desktop/ms682317) method to clean up the package writer and call the [**CoUninitialize**](https://msdn.microsoft.com/library/windows/desktop/ms688715) function.


```C++
if (packageWriter != NULL)
{
    packageWriter->Release();
    packageWriter = NULL;
}
CoUninitialize();
```



## Related topics

<dl> <dt>

**Samples**
</dt> <dt>

[Create app package sample](http://go.microsoft.com/fwlink/p/?linkid=236965)
</dt> <dt>

**Reference**
</dt> <dt>

[**IAppxPackageWriter**](/windows/win32/AppxPackaging/nn-appxpackaging-iappxpackagewriter?branch=master)
</dt> </dl>

 

 



