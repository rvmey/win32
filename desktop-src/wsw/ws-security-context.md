---
title: WS\_SECURITY\_CONTEXT
description: An opaque type used to reference a security context object.
ms.assetid: 8d23357b-bff8-45fe-80ef-df3f3b0edde1
keywords:
- WS_SECURITY_CONTEXT
ms.date: 05/31/2018
ms.topic: article
ms.author: windowssdkdev
ms.prod: windows
ms.technology: desktop
---

# WS\_SECURITY\_CONTEXT

An opaque type used to reference a [security context object](security-context.md).


```C++
typedef struct _WS_SECURITY_CONTEXT WS_SECURITY_CONTEXT;
```



## Remarks

This object is not thread safe. For more information, see [thread safety](thread-safety.md).

## Requirements



|                                     |                                                                                          |
|-------------------------------------|------------------------------------------------------------------------------------------|
| Minimum supported client<br/> | Windows 7 \[desktop apps \| UWP apps\]<br/>                                        |
| Minimum supported server<br/> | Windows Server 2008 R2 \[desktop apps \| UWP apps\]<br/>                           |
| Header<br/>                   | <dl> <dt>WebServices.h</dt> </dl> |



## See also

<dl> <dt>

[Security Context](security-context.md)
</dt> <dt>

[Thread Safety](thread-safety.md)
</dt> </dl>

 

 




