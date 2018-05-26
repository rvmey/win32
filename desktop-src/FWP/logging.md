---
title: Logging
description: Windows Filtering Platform (WFP) provides logging of packet drops and IKE/AuthIP failures.
ms.assetid: 30ff9cf7-bf93-4979-bacd-d76e5dadbef6
ms.date: 05/31/2018
ms.topic: article
ms.author: windowssdkdev
ms.prod: windows
ms.technology: desktop
---

# Logging

The Windows Filtering Platform (WFP) provides logging of packet drops and IKE/AuthIP failures.

The logged events are defined in the [**FWPM\_NET\_EVENT\_TYPE**](/windows/win32/Fwpmtypes/ne-fwpmtypes-fwpm_net_event_type_?branch=master) enumerated type and are as follows.

-   IKE/AuthIP main mode failures.
-   IKE/AuthIP quick mode failures.
-   AuthIP extended mode failures.
-   Packets dropped during classification.
-   Packets dropped by IPsec.

By default, logging for WFP is enabled for unicast inbound packets and for all outbound packets (unicast, multicast, and broadcast). Logging can be enabled for the rest of the packets, or disabled for all packets, through the [**FwpmEngineSetOptions0**](/windows/win32/Fwpmu/nf-fwpmu-fwpmenginesetoption0?branch=master) management function. Event settings persist across reboots.

Logged events are stored in a circular log, that is new events override old ones when the log reaches its maximum size, and can be analyzed using the [event management](fwp-mgmt-functions.md) functions provided by WFP. The event log has a maximum size of 128 KB and it can hold about 100 to 150 events.

Enumeration functions in general, and [**FwpmNetEventEnum0**](/windows/win32/Fwpmu/nf-fwpmu-fwpmneteventenum0?branch=master)/[**FwpmNetEventEnum1**](/windows/win32/Fwpmu/nf-fwpmu-fwpmneteventenum1?branch=master) in particular, take a snapshot of the log at the time the enumeration handle is created. Subsequent calls using the same enumeration handle return the next set of items following those in the last output buffer.

When an application disables WFP logging (by calling [**FwpmEngineSetOptions0**](/windows/win32/Fwpmu/nf-fwpmu-fwpmenginesetoption0?branch=master)) all applications are affected. The event log is not cleaned up until an application re-enables WFP logging, but the event log cannot be queried before then.

The WFP event log is emptied after a reboot.

 

 



