---
title: System.Contact.country property
description: Gets the country name associated with the contact.
ms.assetid: cace6268-3b2c-49da-b67a-ba6979f4cf12
keywords:
- country property Windows Sidebar
- country property Windows Sidebar , System.Contact object
- System.Contact object Windows Sidebar , country property
topic_type:
- apiref
api_name:
- System.Contact.country
api_location:
- Sidebar.Exe
api_type:
- COM
ms.date: 05/31/2018
ms.topic: article
ms.author: windowssdkdev
ms.prod: windows
ms.technology: desktop
---

# System.Contact.country property

\[ The Windows Gadget Platform/Sidebar is available for use in the operating systems specified in the Requirements section. It may be altered or unavailable in subsequent versions. \]

Gets the country name associated with the contact.

This property is read-only.

## Syntax


```JScript
strcountry = System.Contact.country
```



## Property value

A **String** that receives the name of the country.

## Remarks

Individual contacts are accessible through the [**Contacts**](system-contactmanager-contacts.md) collection of [**System.ContactManager**](system-contactmanager.md).

## Examples

The following example demonstrates how to access a contact in the [**Contacts**](system-contactmanager-contacts.md) collection and get a specific property for that contact.


```JScript
// Instantiate a Contacts object to search.
oContact = System.ContactManager.Contacts;

// Iterate through all contacts.
for (var i = 0; i < oContact.count; i++)
{
    var sSearchResult = oContact.item(i).country;
    // Add search result to main display string.
    sOutput += sSearchResult;
}
```



## Requirements



|                                     |                                                                                                                |
|-------------------------------------|----------------------------------------------------------------------------------------------------------------|
| Minimum supported client<br/> | Windows Vista \[desktop apps only\]<br/>                                                                 |
| Minimum supported server<br/> | Windows Server 2008 \[desktop apps only\]<br/>                                                           |
| End of client support<br/>    | Windows 7<br/>                                                                                           |
| End of server support<br/>    | Windows Server 2008<br/>                                                                                 |
| IDL<br/>                      | <dl> <dt>Sidebar.idl</dt> </dl>                         |
| DLL<br/>                      | <dl> <dt>Sidebar.Exe (version 1.00 or later)</dt> </dl> |



 

 




