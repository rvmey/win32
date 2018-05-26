---
title: ProtectedFileStream.FlushAsync method
description: Flushes the data asynchronously to the protected file.
audience: developer
author: REDMOND\\bruceper
manager: REDMOND\\mbaldwin
ms.assetid: MMicrosoft.RightsManagement.ProtectedFileStream.FlushAsync
ms.prod: windows-server-dev
ms.technology: active-directory-rights-management
ms.tgt_platform: multiple
keywords:
- FlushAsync method
- FlushAsync method, ProtectedFileStream class
- ProtectedFileStream class, FlushAsync method
topic_type:
- apiref
api_name:
- Microsoft.RightsManagement.ProtectedFileStream.FlushAsync
api_location:
- Microsoft.RightsManagement.dll
api_type:
- Assembly
ms.date: 05/31/2018
ms.topic: article
ms.author: windowssdkdev
---

# ProtectedFileStream.FlushAsync method

Flushes the data asynchronously to the protected file. Implements the [IOutputStream.FlushAsync](https://msdn.microsoft.com/library/windows/apps/windows.storage.streams.ioutputstream.flushasync.aspx) method.

## Syntax


```C++
public:
virtual IAsyncOperation<bool> FlushAsync()
```



## Parameters

This method has no parameters.

## Return value

Type: [IAsyncOperation&lt;Boolean&gt;](https://msdn.microsoft.com/library/windows/apps/br206598.aspx)

The stream flush operation. **null** is returned if an exception occurs. Upon completion, **IAsyncOperation.GetResults** returns **True** if the file has been successfully flushed; otherwise, **false**.

## Remarks

> \[!Warning\]  
> To avoid data loss and/or corruption, **FlushAsync** must be called before object disposal.

 

## Requirements



|                                     |                                                                                                             |
|-------------------------------------|-------------------------------------------------------------------------------------------------------------|
| Minimum supported client<br/> | None supported<br/>                                                                                   |
| Minimum supported server<br/> | None supported<br/>                                                                                   |
| Minimum supported phone<br/>  | Windows Phone 8.1<br/>                                                                                |
| Namespace<br/>                | Microsoft::RightsManagement<br/>                                                                      |
| Metadata<br/>                 | <dl> <dt>Microsoft.RightsManagement.winmd</dt> </dl> |



## See also

<dl> <dt>

[**ProtectedFileStream**](protectedfilestream.md)
</dt> </dl>

 

 




