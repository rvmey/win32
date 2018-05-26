---
Description: The GetRealState method retrieves the filter state.
ms.assetid: d31c5c0b-6220-4d2e-a81a-d16b7d513c87
title: CBaseRenderer.GetRealState method
ms.date: 05/31/2018
ms.topic: article
ms.author: windowssdkdev
ms.prod: windows
ms.technology: desktop
---

# CBaseRenderer.GetRealState method

The `GetRealState` method retrieves the filter state.

## Syntax


```C++
FILTER_STATE GetRealState();
```



## Parameters

This method has no parameters.

## Return value

Returns the value of [**CBaseFilter::m\_State**](cbasefilter-m-state.md). The value is a member of the [**FILTER\_STATE**](/windows/win32/strmif/ne-strmif-_filterstate?branch=master) enumerated type.

## Remarks

This method provides a simpler alternative to the [**CBaseRenderer::GetState**](cbaserenderer-getstate.md) method, for internal use.

## Requirements



|                    |                                                                                                                                                                                            |
|--------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Header<br/>  | <dl> <dt>Renbase.h (include Streams.h)</dt> </dl>                                                                                   |
| Library<br/> | <dl> <dt>Strmbase.lib (retail builds); </dt> <dt>Strmbasd.lib (debug builds)</dt> </dl> |



## See also

<dl> <dt>

[**CBaseRenderer Class**](cbaserenderer.md)
</dt> </dl>

 

 



