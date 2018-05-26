---
Description: The Invoke method provides access to methods and properties exposed by an object.
ms.assetid: d9539b89-b7c2-4b4d-b6d6-6275cc6d7e7c
title: CDeferredCommand.Invoke method
ms.date: 05/31/2018
ms.topic: article
ms.author: windowssdkdev
ms.prod: windows
ms.technology: desktop
---

# CDeferredCommand.Invoke method

The `Invoke` method provides access to methods and properties exposed by an object.

## Syntax


```C++
HRESULT Invoke();
```



## Parameters

This method has no parameters.

## Return value

Returns VFW\_E\_ALREADY\_CANCELLED if **m\_pQueue** is **NULL**. Otherwise, returns the **HRESULT** resulting from a call to **IDispatch::GetTypeInfo** or **IUnknown::QueryInterface**.

## Requirements



|                    |                                                                                                                                                                                            |
|--------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Header<br/>  | <dl> <dt>Ctlutil.h (include Streams.h)</dt> </dl>                                                                                   |
| Library<br/> | <dl> <dt>Strmbase.lib (retail builds); </dt> <dt>Strmbasd.lib (debug builds)</dt> </dl> |



## See also

<dl> <dt>

[**CDeferredCommand Class**](cdeferredcommand.md)
</dt> </dl>

 

 



