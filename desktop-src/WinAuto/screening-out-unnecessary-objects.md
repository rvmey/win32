---
title: Screening Out Unnecessary Objects
description: If you use Inspect to examine a simple control such as an OK push button in the Microsoft WordPad accessory, you can see that these parent window objects also contain several invisible child objects.
ms.assetid: 30884e11-cc73-4bb8-9d9e-b9f1b53c4193
ms.date: 05/31/2018
ms.topic: article
ms.author: windowssdkdev
ms.prod: windows
ms.technology: desktop
---

# Screening Out Unnecessary Objects

If you use [Inspect](inspect-objects.md) to examine a simple control such as an OK push button in the Microsoft WordPad accessory, you can see that these parent window objects also contain several invisible child objects. These invisible objects have the same window class name as the control and have the [State property](state-property.md) of [**STATE\_SYSTEM\_INVISIBLE**](object-state-constants.md#state-system-invisible). The following table lists the invisible child objects that Microsoft Active Accessibility creates for the control.



| Name          | Role                                                                  | ChildCount |
|---------------|-----------------------------------------------------------------------|------------|
| "System"      | [**ROLE\_SYSTEM\_MENUBAR**](object-roles.md#role-system-menubar)     | 0          |
| None          | [**ROLE\_SYSTEM\_TITLEBAR**](object-roles.md#role-system-titlebar)   | 5          |
| "Application" | [**ROLE\_SYSTEM\_MENUBAR**](object-roles.md#role-system-menubar)     | 0          |
| "Vertical"    | [**ROLE\_SYSTEM\_SCROLLBAR**](object-roles.md#role-system-scrollbar) | 5          |
| "Horizontal"  | [**ROLE\_SYSTEM\_SCROLLBAR**](object-roles.md#role-system-scrollbar) | 5          |
| "Size Box"    | [**ROLE\_SYSTEM\_GRIP**](object-roles.md#role-system-grip)           | 0          |



 

Client developers must identify and filter out these parent window objects and invisible child objects because they do not provide meaningful information to end users.

 

 



