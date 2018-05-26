---
title: ClusResources.Count property
description: Returns the number of objects in the ClusResources collection.
audience: developer
author: REDMOND\\markl
manager: REDMOND\\markl
ms.assetid: 6c9ff4bd-8474-4e88-b70e-bc9e661382ab
ms.prod: windows-server-dev
ms.technology: failover-clustering
ms.tgt_platform: multiple
keywords:
- Count property Failover Cluster
- Count property Failover Cluster , ClusResources collection
- ClusResources collection Failover Cluster , Count property
topic_type:
- apiref
api_name:
- ClusResources.Count
api_location:
- MsClus.dll
api_type:
- COM
ms.date: 05/31/2018
ms.topic: article
ms.author: windowssdkdev
---

# ClusResources.Count property

\[The **Count** property is available for use in the operating systems specified in the Requirements section. It may be altered or unavailable in subsequent versions.\]

Returns the number of objects in the [**ClusResources**](clusresources-collection.md) collection.

This property is read-only.

## Syntax


```VB
ClusResources.Count
```



## Property value

**Long** indicating the number of objects in the collection.

## Requirements



|                                     |                                                                                       |
|-------------------------------------|---------------------------------------------------------------------------------------|
| Minimum supported client<br/> | None supported<br/>                                                             |
| Minimum supported server<br/> | Windows Server 2008 Enterprise, Windows Server 2008 Datacenter<br/>             |
| Header<br/>                   | <dl> <dt>MsClus.h</dt> </dl>   |
| IDL<br/>                      | <dl> <dt>MsClus.idl</dt> </dl> |
| Type library<br/>             | <dl> <dt>MsClus.tlb</dt> </dl> |
| DLL<br/>                      | <dl> <dt>MsClus.dll</dt> </dl> |
| IID<br/>                      | IID\_ISClusResources is defined as F2E6070C-2631-11D1-89F1-00A0C90D061E<br/>    |



## See also

<dl> <dt>

[**ClusResources**](clusresources-collection.md)
</dt> </dl>

 

 




