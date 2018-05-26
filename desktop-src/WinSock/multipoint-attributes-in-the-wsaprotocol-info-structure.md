---
Description: Multipoint attributes in the WSAPROTOCOL\_INFO structure include XP1\_SUPPORT\_MULTIPOINT, XP1\_MULTIPOINT\_CONTROL\_PLANE, and XP1\_MULTIPOINT\_DATA\_PLANE.
ms.assetid: f1bd5aa1-e705-4eaf-9436-fed0ea03f113
title: Multipoint Attributes in the WSAPROTOCOL\_INFO Structure
ms.date: 05/31/2018
ms.topic: article
ms.author: windowssdkdev
ms.prod: windows
ms.technology: desktop
---

# Multipoint Attributes in the WSAPROTOCOL\_INFO Structure

Three attribute parameters are defined in the [**WSAPROTOCOL\_INFO**](/windows/win32/Winsock2/?branch=master) structure in order to distinguish the different schemes used in the control and data planes, respectively:

-   XP1\_SUPPORT\_MULTIPOINT with a value of 1 indicates this protocol entry supports multipoint communications, and that the following two parameters are meaningful.
-   XP1\_MULTIPOINT\_CONTROL\_PLANE indicates whether the control plane is rooted (value = 1) or nonrooted (value = 0).
-   XP1\_MULTIPOINT\_DATA\_PLANE indicates whether the data plane is rooted (value = 1) or nonrooted (value = 0).

Two [**WSAPROTOCOL\_INFO**](/windows/win32/Winsock2/?branch=master) entries would be present if a multipoint protocol supported both rooted and nonrooted data planes, one entry for each.

 

 


