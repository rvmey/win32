---
Description: Writes a string property.
ms.assetid: FF063DFE-FD80-4E30-8289-5B40642C867F
title: IPrinterPropertyBagSetString method
ms.date: 05/31/2018
ms.topic: article
ms.author: windowssdkdev
ms.prod: windows
ms.technology: desktop
---

# IPrinterPropertyBag::SetString method

Writes a string property.

## Syntax


```C++
HRESULT SetString(
  [in] BSTR bstrName,
  [in] BSTR bstrValue
);
```



## Parameters

<dl> <dt>

*bstrName* \[in\]
</dt> <dd>

The property to set.

</dd> <dt>

*bstrValue* \[in\]
</dt> <dd>

The property value to set.

</dd> </dl>

## Return value

This method returns an **HRESULT** value.

## Remarks

In Windows 8.1 a new flag, PRINTER\_ACCESS\_MANAGE\_LIMITED, has been introduced to grant print queue permissions that are more limited than PRINTER\_ACCESS\_ADMINISTER, but more powerful than PRINTER\_ACCESS\_USE.

The permissions are a subset of those associated with PRINTER\_ACCESS\_ADMINISTER. This means that if the currently logged-on user has PRINTER\_ACCESS\_ADMINISTER permission, the user can gain PRINTER\_ACCESS\_MANAGE\_LIMITED access to the queue.

A call to set a property on a queue property bag will fail with ERROR\_ACCESS\_DENIED, if the user does not have the appropriate permission. This behavior was true before PRINTER\_ACCESS\_MANAGE\_LIMITED was introduced, and it's still the current behavior.

## Requirements



|                            |                                                                                                                            |
|----------------------------|----------------------------------------------------------------------------------------------------------------------------|
| Target platform<br/> | <dl> <dt>Desktop</dt> </dl>                                         |
| Header<br/>          | <dl> <dt>Printerextension.h (include Printerextension.h)</dt> </dl> |



## See also

<dl> <dt>

[**IPrinterPropertyBag**](iprinterpropertybag-interface.md)
</dt> </dl>

 

 

[Send comments about this topic to Microsoft](mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback%20%5Bprint\print%5D:%20IPrinterPropertyBag::SetString%20method%20%20RELEASE:%20%285/12/2018%29&body=%0A%0APRIVACY%20STATEMENT%0A%0AWe%20use%20your%20feedback%20to%20improve%20the%20documentation.%20We%20don't%20use%20your%20email%20address%20for%20any%20other%20purpose,%20and%20we'll%20remove%20your%20email%20address%20from%20our%20system%20after%20the%20issue%20that%20you're%20reporting%20is%20fixed.%20While%20we're%20working%20to%20fix%20this%20issue,%20we%20might%20send%20you%20an%20email%20message%20to%20ask%20for%20more%20info.%20Later,%20we%20might%20also%20send%20you%20an%20email%20message%20to%20let%20you%20know%20that%20we've%20addressed%20your%20feedback.%0A%0AFor%20more%20info%20about%20Microsoft's%20privacy%20policy,%20see%20http://privacy.microsoft.com/en-us/default.aspx. "Send comments about this topic to Microsoft")




