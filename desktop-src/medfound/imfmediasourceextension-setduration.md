---
Description: Sets the duration of the media source in 100-nanosecond units.
ms.assetid: dc3dc600-ca81-40da-9edb-0af283ba9221
title: IMFMediaSourceExtensionSetDuration method
ms.date: 05/31/2018
ms.topic: article
ms.author: windowssdkdev
ms.prod: windows
ms.technology: desktop
---

# IMFMediaSourceExtension::SetDuration method

Sets the duration of the media source in 100-nanosecond units.

## Syntax


```C++
HRESULT SetDuration(
  [in] double duration
);
```



## Parameters

<dl> <dt>

*duration* \[in\]
</dt> <dd>

The duration of the media source in 100-nanosecond units.

</dd> </dl>

## Return value

If this method succeeds, it returns **S\_OK**. Otherwise, it returns an **HRESULT** error code.

## Requirements



|                                     |                                                                                              |
|-------------------------------------|----------------------------------------------------------------------------------------------|
| Minimum supported client<br/> | Windows 8.1 \[desktop apps only\]<br/>                                                 |
| Minimum supported server<br/> | Windows Server 2012 R2 \[desktop apps only\]<br/>                                      |
| IDL<br/>                      | <dl> <dt>Mfmediaengine.idl</dt> </dl> |



## See also

<dl> <dt>

[**IMFMediaSourceExtension**](/windows/win32/mfmediaengine/nn-mfmediaengine-imfmediasourceextension?branch=master)
</dt> </dl>

 

 



