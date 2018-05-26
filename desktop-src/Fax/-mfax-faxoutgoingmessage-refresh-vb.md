---
Description: Refreshes FaxOutgoingMessage object information from the fax server. When the Refresh method is called, any configuration changes made after the last Save method call are lost.
ms.assetid: 4f39ead7-2546-4c38-af87-3c338342ebae
title: FaxOutgoingMessage.Refresh method
ms.date: 05/31/2018
ms.topic: article
ms.author: windowssdkdev
ms.prod: windows
ms.technology: desktop
---

# FaxOutgoingMessage.Refresh method

Refreshes [**FaxOutgoingMessage**](-mfax-faxoutgoingmessage.md) object information from the fax server. When the **Refresh** method is called, any configuration changes made after the last [**Save**](-mfax-faxoutgoingmessage-save-vb.md) method call are lost.

> [!Note]  
> This method is supported only on Windows Vista and later.

 

## Syntax


```VB
FaxOutgoingMessage.Refresh() As Long
```



## Parameters

This method has no parameters.

## Remarks

To use this method, a user must have the [****far2QUERY\_CONFIG****](/windows/previous-versions/FaxComex/ne-faxcomex-fax_access_rights_enum_2?branch=master) access rights.

## Requirements



|                                     |                                                                                         |
|-------------------------------------|-----------------------------------------------------------------------------------------|
| Minimum supported client<br/> | Windows Vista \[desktop apps only\]<br/>                                          |
| Minimum supported server<br/> | Windows Server 2008 \[desktop apps only\]<br/>                                    |
| Header<br/>                   | <dl> <dt>FaxComex.h</dt> </dl>   |
| DLL<br/>                      | <dl> <dt>Fxscomex.dll</dt> </dl> |



## See also

<dl> <dt>

[**FaxOutgoingMessage**](-mfax-faxoutgoingmessage.md)
</dt> <dt>

[**IFaxOutgoingMessage2**](/windows/previous-versions/FaxComex/nn-faxcomex-ifaxoutgoingmessage2?branch=master)
</dt> </dl>

 

 



