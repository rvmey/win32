---
Description: You can use the properties of the SWbemQualifier object to represent a single qualifier of a WMI class, instance, property, or method parameter. This object cannot be created by the VBScript CreateObject call.
audience: developer
author: REDMOND\\markl
manager: REDMOND\\markl
ms.assetid: b5dbe98a-e1d8-4679-a563-c88760d08b79
ms.prod: windows-server-dev
ms.technology: windows-management-instrumentation
ms.tgt_platform: multiple
title: SWbemQualifier object
ms.date: 05/31/2018
ms.topic: interface
ms.author: windowssdkdev
---

# SWbemQualifier object

You can use the properties of the **SWbemQualifier** object to represent a single qualifier of a WMI class, instance, property, or method parameter. This object cannot be created by the VBScript [CreateObject](creating-an-object-using-vbscript.md) call.

## Members

The **SWbemQualifier** object has these types of members:

-   [Properties](#properties)

### Properties

The **SWbemQualifier** object has these properties.



| Property                                                                       | Access type           | Description                                                                                           |
|:-------------------------------------------------------------------------------|:----------------------|:------------------------------------------------------------------------------------------------------|
| [**IsAmended**](swbemqualifier-isamended.md)<br/>                       | Read-only<br/>  | Boolean value that indicates if this qualifier has been localized using a merge operation.<br/> |
| [**IsLocal**](swbemqualifier-islocal.md)<br/>                           | Read-only<br/>  | Boolean value that indicates if this qualifier is local.<br/>                                   |
| [**IsOverridable**](swbemqualifier-isoverridable.md)<br/>               | Read/write<br/> | Boolean value that indicates if this qualifier can be overridden when propagated.<br/>          |
| [**Name**](swbemqualifier-name.md)<br/>                                 | Read-only<br/>  | Name of this qualifier.<br/>                                                                    |
| [**PropagatesToInstance**](swbemqualifier-propagatestoinstance.md)<br/> | Read/write<br/> | Boolean value that indicates if this qualifier can be propagated to an instance.<br/>           |
| [**PropagatesToSubClass**](swbemqualifier-propagatestosubclass.md)<br/> | Read-only<br/>  | Boolean value that indicates if this qualifier can be propagated to a subclass.<br/>            |
| [**Value**](swbemqualifier-value.md)<br/>                               | Read/write<br/> | Variant value of this qualifier. This is the default property of this object.<br/>              |



 

## Requirements



|                                     |                                                                                         |
|-------------------------------------|-----------------------------------------------------------------------------------------|
| Minimum supported client<br/> | Windows Vista<br/>                                                                |
| Minimum supported server<br/> | Windows Server 2008<br/>                                                          |
| Header<br/>                   | <dl> <dt>Wbemdisp.h</dt> </dl>   |
| Type library<br/>             | <dl> <dt>Wbemdisp.tlb</dt> </dl> |
| DLL<br/>                      | <dl> <dt>Wbemdisp.dll</dt> </dl> |
| CLSID<br/>                    | CLSID\_SWbemQualifier<br/>                                                        |
| IID<br/>                      | IID\_ISWbemQualifier<br/>                                                         |



## See also

<dl> <dt>

[Scripting API Objects](scripting-api-objects.md)
</dt> </dl>

 

 



