---
title: ClusResource.PrivateROProperties property
description: Returns the read-only private properties of a resource.
audience: developer
author: REDMOND\\markl
manager: REDMOND\\markl
ms.assetid: 88869f08-db47-4661-bd23-7fe0bb491fa3
ms.prod: windows-server-dev
ms.technology: failover-clustering
ms.tgt_platform: multiple
keywords:
- PrivateROProperties property Failover Cluster
- PrivateROProperties property Failover Cluster , ClusResource object
- ClusResource object Failover Cluster , PrivateROProperties property
topic_type:
- apiref
api_name:
- ClusResource.PrivateROProperties
api_location:
- MsClus.dll
api_type:
- COM
ms.date: 05/31/2018
ms.topic: article
ms.author: windowssdkdev
---

# ClusResource.PrivateROProperties property

\[The **PrivateROProperties** property is available for use in the operating systems specified in the Requirements section. It may be altered or unavailable in subsequent versions.\]

Returns the read-only [private properties](private-properties.md) of a [resource](resources.md).

This property is read-only.

## Syntax


```VB
ClusResource.PrivateROProperties
```



## Property value

A [**ClusProperties**](clusproperties-collection.md) collection to receive the read-only private properties of the resource.

## Requirements



|                                     |                                                                                       |
|-------------------------------------|---------------------------------------------------------------------------------------|
| Minimum supported client<br/> | None supported<br/>                                                             |
| Minimum supported server<br/> | Windows Server 2008 Enterprise, Windows Server 2008 Datacenter<br/>             |
| Header<br/>                   | <dl> <dt>MsClus.h</dt> </dl>   |
| IDL<br/>                      | <dl> <dt>MsClus.idl</dt> </dl> |
| Type library<br/>             | <dl> <dt>MsClus.tlb</dt> </dl> |
| DLL<br/>                      | <dl> <dt>MsClus.dll</dt> </dl> |
| IID<br/>                      | IID\_ISClusResource is defined as F2E6070A-2631-11D1-89F1-00A0C90D061E<br/>     |



## See also

<dl> <dt>

[**ClusResource**](clusresource-object.md)
</dt> <dt>

[**ClusProperties**](clusproperties-collection.md)
</dt> </dl>

 

 




