---
Description: Create an effect pool asynchronously.
ms.assetid: 50c55751-26de-4002-9a89-8e5ab59dda79
title: D3DX10CreateAsyncEffectCreateProcessor function
ms.date: 05/31/2018
ms.topic: article
ms.author: windowssdkdev
ms.prod: windows
ms.technology: desktop
---

# D3DX10CreateAsyncEffectCreateProcessor function

Create an effect pool asynchronously.

## Syntax


```C++
HRESULT D3DX10CreateAsyncEffectCreateProcessor(
  _In_        LPCSTR               pFileName,
  _In_  const D3D10_SHADER_MACRO   *pDefines,
  _In_        LPD3D10INCLUDE       pInclude,
  _In_        LPCSTR               pProfile,
  _In_        UINT                 Flags,
  _In_        UINT                 FXFlags,
  _In_        ID3D10Device         *pDevice,
  _In_        ID3D10EffectPool     *pPool,
  _Out_       ID3D10Blob           **ppErrorBuffer,
  _Out_       ID3DX10DataProcessor **ppProcessor
);
```



## Parameters

<dl> <dt>

*pFileName* \[in\]
</dt> <dd>

Type: **[**LPCSTR**](winprog.windows_data_types)**

A string that contains the effect filename.

</dd> <dt>

*pDefines* \[in\]
</dt> <dd>

Type: **const [**D3D10\_SHADER\_MACRO**](/windows/win32/D3D10Shader/?branch=master)\***

A NULL-terminated array of shader macros (see [**D3D10\_SHADER\_MACRO**](/windows/win32/D3D10Shader/?branch=master)); set this to **NULL** to specify no macros.

</dd> <dt>

*pInclude* \[in\]
</dt> <dd>

Type: **[**LPD3D10INCLUDE**](/windows/win32/D3D10Shader/?branch=master)**

A pointer to an include interface (see [**ID3D10Include Interface**](/windows/win32/D3D10Shader/?branch=master)); set this to **NULL** to specify there is no include file.

</dd> <dt>

*pProfile* \[in\]
</dt> <dd>

Type: **[**LPCSTR**](winprog.windows_data_types)**

A string that specifies the [shader profile](direct3dhlsl.dx_graphics_hlsl_models) or shader model.

</dd> <dt>

*Flags* \[in\]
</dt> <dd>

Type: **[**UINT**](winprog.windows_data_types)**

HLSL compile options (see [Shader Flags](d3d10-graphics-reference-effect-constants.md)).

</dd> <dt>

*FXFlags* \[in\]
</dt> <dd>

Type: **[**UINT**](winprog.windows_data_types)**

Effect compile options (see [Compile and Effect Flags](d3d10-graphics-reference-effect-constants.md)).

</dd> <dt>

*pDevice* \[in\]
</dt> <dd>

Type: **[**ID3D10Device**](/windows/win32/D3D10/nn-d3d10-id3d10device?branch=master)\***

A pointer to the device (see [**ID3D10Device Interface**](/windows/win32/D3D10/nn-d3d10-id3d10device?branch=master)) that will use the resources.

</dd> <dt>

*pPool* \[in\]
</dt> <dd>

Type: **[**ID3D10EffectPool**](/windows/win32/D3D10Effect/nn-d3d10effect-id3d10effectpool?branch=master)\***

A pointer to an effect pool (see [**ID3D10EffectPool Interface**](/windows/win32/D3D10Effect/nn-d3d10effect-id3d10effectpool?branch=master)) for sharing variables between effects.

</dd> <dt>

*ppErrorBuffer* \[out\]
</dt> <dd>

Type: **[**ID3D10Blob**](/windows/win32/D3DCommon/nn-d3dcommon-id3d10blob?branch=master)\*\***

The address of a pointer to memory (see [**ID3D10Blob Interface**](/windows/win32/D3DCommon/nn-d3dcommon-id3d10blob?branch=master)) that contains effect compile errors, if there were any.

</dd> <dt>

*ppProcessor* \[out\]
</dt> <dd>

Type: **[**ID3DX10DataProcessor**](id3dx10dataprocessor.md)\*\***

The address of a pointer to the asynchronous-data processor (see [**ID3DX10DataProcessor Interface**](id3dx10dataprocessor.md)).

</dd> </dl>

## Return value

Type: **[**HRESULT**](455d07e9-52c3-4efb-a9dc-2955cbfd38cc)**

The return value is one of the values listed in [Direct3D 10 Return Codes](d3d10-graphics-reference-returnvalues.md).

## Requirements



|                   |                                                                                          |
|-------------------|------------------------------------------------------------------------------------------|
| Header<br/> | <dl> <dt>D3DX10Async.h</dt> </dl> |



## See also

<dl> <dt>

[General Purpose Functions](d3d10-graphics-reference-d3dx10-functions-general-purpose.md)
</dt> </dl>

 

 



