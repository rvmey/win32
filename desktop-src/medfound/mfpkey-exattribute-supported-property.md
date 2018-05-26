---
Description: Specifies whether a Media Foundation transform (MFT) copies attributes from input samples to output samples.
ms.assetid: 039ecb35-9aa9-4e8a-bbbc-042b9c4c874c
title: MFPKEY\_EXATTRIBUTE\_SUPPORTED property
ms.date: 05/31/2018
ms.topic: article
ms.author: windowssdkdev
ms.prod: windows
ms.technology: desktop
---

# MFPKEY\_EXATTRIBUTE\_SUPPORTED property

Specifies whether a Media Foundation transform (MFT) copies attributes from input samples to output samples.



Data type

PROPVARIANT type (vt)

PROPVARIANT member

**VARIANT\_BOOL**

VT\_BOOL

**boolVal**



## Remarks

This attribute can have the following values.



| Value              | Description                                                                                                                                             |
|--------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------|
| **VARIANT\_TRUE**  | The MFT copies attributes from the input samples to the output samples.                                                                                 |
| **VARIANT\_FALSE** | The Media Session copies attributes from input samples to output samples. It does not overwrite any attributes that the MFT sets on the output samples. |



 

To get this attribute, call **QueryInterface** on the MFT for the **IPropertyStore** interface.

The default value is **VARIANT\_FALSE**. If the MFT does not expose the **IPropertyStore** interface, or if this property is not set, treat the value as **VARIANT\_FALSE**.

This property is read-only.

## Examples

The following example returns VARIANT\_TRUE if an MFT copies sample attributes.


```C++
BOOL TransformCopiesSampleAttributes(IMFTransform *pMFT)
{
    BOOL bCopiesAttributes = FALSE;

    IPropertyStore *pProps = NULL;

    HRESULT hr = pMFT->QueryInterface(IID_PPV_ARGS(&amp;pProps));
    
    if (SUCCEEDED(hr))
    {
        PROPVARIANT var;
        hr = pProps->GetValue(MFPKEY_EXATTRIBUTE_SUPPORTED, &amp;var);

        if (SUCCEEDED(hr))
        {
            bCopiesAttributes = 
                (var.vt == VT_BOOL &amp;&amp; var.boolVal == VARIANT_TRUE);

            PropVariantClear(&amp;var);
        }
        pProps->Release();
    }
    return bCopiesAttributes;
}
```



## Requirements



|                                     |                                                                                          |
|-------------------------------------|------------------------------------------------------------------------------------------|
| Minimum supported client<br/> | Windows Vista \[desktop apps only\]<br/>                                           |
| Minimum supported server<br/> | Windows Server 2008 \[desktop apps only\]<br/>                                     |
| Header<br/>                   | <dl> <dt>Mftransform.h</dt> </dl> |



## See also

<dl> <dt>

[Media Foundation Properties](media-foundation-properties.md)
</dt> <dt>

[Sample Attributes](sample-attributes.md)
</dt> <dt>

[**IMFTransform::ProcessOutput**](/windows/win32/mftransform/nf-mftransform-imftransform-processoutput?branch=master)
</dt> </dl>

 

 



