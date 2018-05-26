---
title: Activity GetTraceToolTip method
description: Returns the trace tooltip of the Activity.
ms.assetid: 9ECAFE9D-A3F9-4D1B-AA18-341C438AE692
keywords:
- GetTraceToolTip method Access Execution Engine
- GetTraceToolTip method Access Execution Engine , Activity interface
- Activity interface Access Execution Engine , GetTraceToolTip method
topic_type:
- apiref
api_name:
- Activity.GetTraceToolTip
api_location:
- AxeCore.dll
api_type:
- COM
ms.date: 05/31/2018
ms.topic: article
ms.author: windowssdkdev
ms.prod: windows
ms.technology: desktop
---

# Activity::GetTraceToolTip method

Returns the trace tooltip of the **Activity**.

## Syntax


```C++
virtual HRESULT GetTraceToolTip(
  [out] LPCWSTR *traceToolTip
) const = 0;
```



## Parameters

<dl> <dt>

*traceToolTip* \[out\]
</dt> <dd>

The trace tooltip.

</dd> </dl>

## Return value

If the function succeeds, it returns **S\_OK**. If it fails, it returns an error value.

## Remarks

**Activity** objects hold data from **Iteration/Activities/Activity** elements.

The trace tooltip is the value of element **Activity/Trace/Description/ToolTip**.

## Requirements



|                                     |                                                                                         |
|-------------------------------------|-----------------------------------------------------------------------------------------|
| Minimum supported client<br/> | Windows 7 \[desktop apps only\]<br/>                                              |
| Minimum supported server<br/> | Windows Server 2008 R2 \[desktop apps only\]<br/>                                 |
| Header<br/>                   | <dl> <dt>AxeRuntime.h</dt> </dl> |
| DLL<br/>                      | <dl> <dt>AxeCore.dll</dt> </dl>  |



## See also

<dl> <dt>

[**Activity**](activity-struct.md)
</dt> </dl>

 

 




