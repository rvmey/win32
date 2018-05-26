---
Description: Accesses the .x file data.
ms.assetid: 0e92914b-47b3-4a88-87ba-ce3c14282dbb
title: ID3DXFileDataLock method
ms.date: 05/31/2018
ms.topic: article
ms.author: windowssdkdev
ms.prod: windows
ms.technology: desktop
---

# ID3DXFileData::Lock method

Accesses the .x file data.

## Syntax


```C++
HRESULT Lock(
  [in]       SIZE_T *pSize,
  [in] const VOID   **ppData
);
```



## Parameters

<dl> <dt>

*pSize* \[in\]
</dt> <dd>

Type: **[**SIZE\_T**](winprog.windows_data_types)\***

Pointer to the size of the .x file data.

</dd> <dt>

*ppData* \[in\]
</dt> <dd>

Type: **const VOID\*\***

Address of a pointer to receive the [**ID3DXFileData**](id3dxfiledata.md) file data object's interface pointer. See Remarks.

</dd> </dl>

## Return value

Type: **[**HRESULT**](455d07e9-52c3-4efb-a9dc-2955cbfd38cc)**

If the method succeeds, the return value is S\_OK. If the method fails, the following value will be returned: D3DXFERR\_BADVALUE.

## Remarks

The *ppData* pointer is only valid during a **ID3DXFileData::Lock** ... [**ID3DXFileData::Unlock**](id3dxfiledata--unlock.md) sequence. You can make multiple lock calls. However, you must ensure that the number of lock calls matches the number of unlock calls.

Because file data is not guaranteed to be aligned properly with byte boundaries, you should access *ppData* with UNALIGNED pointers.

Returned parameter values are not guaranteed to be valid due to possible file corruption; therefore, your code should verify the returned parameter values.

## Requirements



|                    |                                                                                       |
|--------------------|---------------------------------------------------------------------------------------|
| Header<br/>  | <dl> <dt>D3DX9Xof.h</dt> </dl> |
| Library<br/> | <dl> <dt>D3dx9.lib</dt> </dl>  |



## See also

<dl> <dt>

[ID3DXFileData](id3dxfiledata.md)
</dt> </dl>

 

 



