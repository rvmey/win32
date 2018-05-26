---
title: CLUSCTL\_RESOURCE\_TYPE\_STORAGE\_GET\_DISKID control code
description: Queries the ID of a disk on the designated node.
audience: developer
author: REDMOND\\markl
manager: REDMOND\\markl
ms.assetid: f2e127d1-0358-4fdb-917a-05da5317ff0a
ms.prod: windows-server-dev
ms.technology: failover-clustering
ms.tgt_platform: multiple
keywords:
- CLUSCTL_RESOURCE_TYPE_STORAGE_GET_DISKID control code Failover Cluster
topic_type:
- apiref
api_name:
- CLUSCTL_RESOURCE_TYPE_STORAGE_GET_DISKID
api_location:
- ClusAPI.h
api_type:
- HeaderDef
ms.date: 05/31/2018
ms.topic: article
ms.author: windowssdkdev
---

# CLUSCTL\_RESOURCE\_TYPE\_STORAGE\_GET\_DISKID control code

Queries the ID of a disk on the designated node. Applications use this control code as a parameter to [**ClusterResourceTypeControl**](/windows/previous-versions/ClusAPI/nf-clusapi-clusterresourcetypecontrol?branch=master) function, and [resource DLLs](resource-dlls.md) receive the control code as a parameter to the [**ResourceTypeControl**](/windows/previous-versions/ResApi/nc-resapi-presource_type_control_routine?branch=master) callback function.


```C++
ClusterResourceTypeControl( hCluster,                                 // cluster handle
                            lpszResTypeName,                          // resource type name
                            hHostNode,                                // optional host node
                            CLUSCTL_RESOURCE_TYPE_STORAGE_GET_DISKID, // this control code
                            lpInBuffer,                               // input buffer: file path
                            cbInBufferSize,                           // input buffer size
                            lpOutBuffer,                              // output buffer: Disk ID
                            cbOutBufferSize,                          // allocated buffer size
                            lpcbBytesReturned );                      // size of returned data
```



## Parameters

The following control code function and DLL support parameters are specific to this control code. For complete parameter descriptions, see [**ClusterResourceTypeControl**](/windows/previous-versions/ClusAPI/nf-clusapi-clusterresourcetypecontrol?branch=master) or [**ResourceTypeControl**](/windows/previous-versions/ResApi/nc-resapi-presource_type_control_routine?branch=master).

<dl> <dt>

*lpInBuffer* 
</dt> <dd>

A null-terminated string representing the file path on the target disk.

</dd> <dt>

*lpOutBuffer* 
</dt> <dd>

Points to the disk id in the following format.

-   A 32-bit integer indicating ID type. Valid values for this field are 0x00000001 for MBR disks, 0x00000002 for GPT disks, and 0x00001388 for disks whose partition type is unknown.
-   A 32-bit integer if the preceding ID type is MBR or a 128-bitfield if the preceding ID type is GPT.

</dd> </dl>

## Return value

[**ClusterResourceTypeControl**](/windows/previous-versions/ClusAPI/nf-clusapi-clusterresourcetypecontrol?branch=master) returns one of the following values.

<dl> <dt>

**ERROR\_SUCCESS**
</dt> <dd>

0

The operation completed successfully.

</dd> <dt>

**ERROR\_MORE\_DATA**
</dt> <dd>

234 (0xEA)

More data is available. The output buffer pointed to by *lpOutBuffer* was not large enough to hold the data resulting from the operation. The *lpcbBytesReturned* parameter points to the size required for the output buffer.

</dd> <dt>

**[System error code](https://msdn.microsoft.com/library/windows/desktop/ms681381)**
</dt> <dd>

If any other value is returned, then the operation failed. The value of *lpcbBytesReturned* is unreliable.

</dd> </dl>

## Remarks

ClusAPI.h defines the 32 bits of CLUSCTL\_RESOURCE\_TYPE\_STORAGE\_GET\_DISKID (0x02000205) as follows.



| Component      | Bit location | Value                                   |
|----------------|--------------|-----------------------------------------|
| Object code    | 24 31        | **CLUS\_OBJECT\_RESOURCE\_TYPE** (0x2)  |
| Global bit     | 23           | **CLUS\_NOT\_GLOBAL** (0x0)             |
| Modify bit     | 22           | **CLUS\_NO\_MODIFY** (0x0)              |
| User bit       | 21           | **CLCTL\_CLUSTER\_BASE** (0x0)          |
| Type bit       | 20           | External (0x0)                          |
| Operation code | 0 23         | **CLCTL\_STORAGE\_GET\_DISKID** (0x205) |
| Access code    | 0 1          | **CLUS\_ACCESS\_READ** (0x1)            |



 

For more information, see [Control Code Architecture](control-code-architecture.md).

## Requirements



|                                     |                                                                                      |
|-------------------------------------|--------------------------------------------------------------------------------------|
| Minimum supported client<br/> | None supported<br/>                                                            |
| Minimum supported server<br/> | Windows Server 2008 Datacenter, Windows Server 2008 Enterprise<br/>            |
| Header<br/>                   | <dl> <dt>ClusAPI.h</dt> </dl> |



## See also

<dl> <dt>

[External Resource Type Control Codes](external-resource-type-control-codes.md)
</dt> <dt>

[**ClusterResourceTypeControl**](/windows/previous-versions/ClusAPI/nf-clusapi-clusterresourcetypecontrol?branch=master)
</dt> <dt>

[**ResourceTypeControl**](/windows/previous-versions/ResApi/nc-resapi-presource_type_control_routine?branch=master)
</dt> </dl>

 

 




