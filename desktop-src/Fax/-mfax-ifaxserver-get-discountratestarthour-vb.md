---
Description: Sets or retrieves the DiscountRateStartHour property for a FaxServer object. The DiscountRateStartHour property is a number that represents the hour the discount period begins. The discount period applies only to outgoing fax transmissions.
ms.assetid: 1ba6f885-08a2-4ee5-9120-c9da3e01c570
title: FaxServer.DiscountRateStartHour property
ms.date: 05/31/2018
ms.topic: article
ms.author: windowssdkdev
ms.prod: windows
ms.technology: desktop
---

# FaxServer.DiscountRateStartHour property

Sets or retrieves the **DiscountRateStartHour** property for a [FaxServer](-mfax-faxserver-client.md) object. The **DiscountRateStartHour** property is a number that represents the hour the discount period begins. The discount period applies only to outgoing fax transmissions.

This property is read/write.

## Syntax


```VB
Property DiscountRateStartHour As Integer
```



## Property value

An **Integer** that specifies or receives the hour the discount period begins. Valid values for this parameter are 0 through 23.

## Remarks

To save on transmission costs, a user can queue a fax job and request that the fax server send the transmission during the discount rate period. For more information, see [**FaxDoc.DiscountSend Property**](-mfax-ifaxdoc-get-discountsend-vb.md).

The **DiscountRateStartHour**, [**DiscountRateStartMinute**](-mfax-ifaxserver-get-discountratestartminute-vb.md), [**DiscountRateEndHour**](-mfax-ifaxserver-get-discountrateendhour-vb.md), and [**DiscountRateEndMinute**](-mfax-ifaxserver-get-discountrateendminute-vb.md) properties represent local time.

If the time the discount rate period ends is less than the time the discount rate period begins, the discount rate period extends into the next day. For example, if the discount rate period begins at 9:00 P.M. and ends at 7:00 A.M., the discount rate period begins in the evening and continues until the morning of the following day.

## Requirements



|                                     |                                                                                       |
|-------------------------------------|---------------------------------------------------------------------------------------|
| Minimum supported client<br/> | Windows 2000 Professional \[desktop apps only\]<br/>                            |
| Minimum supported server<br/> | Windows 2000 Server \[desktop apps only\]<br/>                                  |
| Header<br/>                   | <dl> <dt>Faxcom.h</dt> </dl>   |
| DLL<br/>                      | <dl> <dt>Faxcom.dll</dt> </dl> |



## See also

<dl> <dt>

[**FaxServer**](-mfax-faxserver-object-visual-basic-.md)
</dt> <dt>

[Fax Service Client API for Windows 2000](-mfax-fax-service-client-api-for-windows-2000.md)
</dt> <dt>

[Fax Service Client API Interfaces](-mfax-fax-service-client-api-interfaces.md)
</dt> <dt>

[FaxServer](-mfax-faxserver-client.md)
</dt> <dt>

[**DiscountRateStartMinute**](-mfax-ifaxserver-get-discountratestartminute-vb.md)
</dt> <dt>

[**DiscountRateEndHour**](-mfax-ifaxserver-get-discountrateendhour-vb.md)
</dt> <dt>

[**DiscountRateEndMinute**](-mfax-ifaxserver-get-discountrateendminute-vb.md)
</dt> <dt>

[**DiscountSend**](-mfax-ifaxdoc-get-discountsend-vb.md)
</dt> </dl>

 

 



