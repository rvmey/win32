---
title: Toolbar Control (MSAA UI Element Reference)
description: A toolbar control contains buttons that carry out menu commands and is usually contained within a window below the menu bar.
ms.assetid: 2ded8753-0102-4d0b-bf92-0d1084aeca59
ms.date: 05/31/2018
ms.topic: article
ms.author: windowssdkdev
ms.prod: windows
ms.technology: desktop
---

# Toolbar Control (MSAA UI Element Reference)

> [!Note]  
> This topic describes **Toolbar Control** objects for purposes of MSAA UI Element Reference. How to create **Toolbar Control** objects in various UI frameworks is not described here. See the API reference documentation for the UI framework you're using.

 

A toolbar control contains buttons that carry out menu commands and is usually contained within a window below the menu bar.

The window class name for a toolbar control is TOOLBARCLASSNAME, which is defined as "ToolbarWindow32" in Commctrl.h.

## IAccessible Methods

A toolbar control supports the following [**IAccessible**](/windows/win32/oleacc/nn-oleacc-iaccessible?branch=master) methods:



| Method                                                                    | Comments                                                                                                                                                                                                                                                                                                                 |
|---------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| [**accDoDefaultAction**](/windows/win32/Oleacc/nf-oleacc-iaccessible-accdodefaultaction?branch=master) | The toolbar itself does support the [**accDoDefaultAction**](/windows/win32/Oleacc/nf-oleacc-iaccessible-accdodefaultaction?branch=master) method. For the buttons on the toolbar, **accDoDefaultAction** calls [**PostMessage**](https://msdn.microsoft.com/library/windows/desktop/ms644944) with the [**BM\_CLICK**](https://msdn.microsoft.com/library/windows/desktop/bb775985) message to click the specified button. |
| [**accHitTest**](/windows/win32/Oleacc/nf-oleacc-iaccessible-acchittest?branch=master)                 |                                                                                                                                                                                                                                                                                                                          |
| [**accLocation**](/windows/win32/Oleacc/nf-oleacc-iaccessible-acclocation?branch=master)               |                                                                                                                                                                                                                                                                                                                          |
| [**accNavigate**](/windows/win32/Oleacc/nf-oleacc-iaccessible-accnavigate?branch=master)               |                                                                                                                                                                                                                                                                                                                          |
| [**accSelect**](/windows/win32/Oleacc/nf-oleacc-iaccessible-accselect?branch=master)                   |                                                                                                                                                                                                                                                                                                                          |



 

## IAccessible Properties

A toolbar control supports the following [**IAccessible**](/windows/win32/oleacc/nn-oleacc-iaccessible?branch=master) properties:



| Property                                                                             | Comments                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                    |
|--------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| [**get\_accChild**](/windows/win32/Oleacc/nf-oleacc-iaccessible-get_accchild?branch=master)                       |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                             |
| [**get\_accChildCount**](/windows/win32/Oleacc/nf-oleacc-iaccessible-get_accchildcount?branch=master)             | The **ChildCount** property is the number of controls contained in the toolbar.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                             |
| [**get\_accDefaultAction**](/windows/win32/Oleacc/nf-oleacc-iaccessible-get_accdefaultaction?branch=master)       | The toolbar object itself does not have a **DefaultAction** property. The **DefaultAction** property for toolbar buttons depends on the toolbar button style. Buttons with the style TBSTYLE\_DROPDOWN have "Open" as their **DefaultAction** property. The **DefaultAction** property for all other toolbar buttons is "Press".                                                                                                                                                                                                                                                                                                                                                                                                                            |
| [**get\_accDescription**](/windows/win32/Oleacc/nf-oleacc-iaccessible-get_accdescription?branch=master)           |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                             |
| [**get\_accFocus**](/windows/win32/Oleacc/nf-oleacc-iaccessible-get_accfocus?branch=master)                       |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                             |
| [**get\_accHelp**](/windows/win32/Oleacc/nf-oleacc-iaccessible-get_acchelp?branch=master)                         |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                             |
| [**get\_accHelpTopic**](/windows/win32/Oleacc/nf-oleacc-iaccessible-get_acchelptopic?branch=master)               |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                             |
| [**get\_accKeyboardShortcut**](/windows/win32/Oleacc/nf-oleacc-iaccessible-get_acckeyboardshortcut?branch=master) | Toolbars do not have keyboard shortcuts. However, if the window text for the toolbar contains an ampersand (&) character, Microsoft Active Accessibility returns a non-Null string as the **KeyboardShortcut** property.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                    |
| [**get\_accName**](/windows/win32/Oleacc/nf-oleacc-iaccessible-get_accname?branch=master)                         | The **Name** property for the toolbar is obtained from the control's window text (or caption). This text is not displayed with the toolbar, so server developers must provide meaningful text in the control's resource definition statement to help users of client utilities identify the control. The window text can be set by using the [**SetWindowText**](https://msdn.microsoft.com/library/windows/desktop/ms633546) function.                                                                                                                                                                                                                                                                                                                                                            |
| [**get\_accParent**](/windows/win32/Oleacc/nf-oleacc-iaccessible-get_accparent?branch=master)                     | The **Parent** property is a window ( [**ROLE\_SYSTEM\_WINDOW**](object-roles.md#role-system-window) ) that surrounds the control and has the same **Name** property and window class name as the control.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |
| [**get\_accRole**](/windows/win32/Oleacc/nf-oleacc-iaccessible-get_accrole?branch=master)                         | The **Role** property is [**ROLE\_SYSTEM\_TOOLBAR**](object-roles.md#role-system-toolbar).                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |
| [**get\_accSelection**](/windows/win32/Oleacc/nf-oleacc-iaccessible-get_accselection?branch=master)               |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                             |
| [**get\_accState**](/windows/win32/Oleacc/nf-oleacc-iaccessible-get_accstate?branch=master)                       | The [value](object-state-constants.md) for the **State** property for the toolbar itself is zero, which means the object is visible. Possible values for the **State** property of the toolbar buttons are: [**STATE\_SYSTEM\_INVISIBLE**](object-state-constants.md#state-system-invisible) or<br/> [**STATE\_SYSTEM\_UNAVAILABLE**](object-state-constants.md#state-system-unavailable) \| [**STATE\_SYSTEM\_INVISIBLE**](object-state-constants.md#state-system-invisible) \| [**STATE\_SYSTEM\_MOVEABLE**](object-state-constants.md#state-system-moveable) \| [**STATE\_SYSTEM\_FOCUSED**](object-state-constants.md#state-system-focused) \| [**STATE\_SYSTEM\_FOCUSABLE**](object-state-constants.md#state-system-focusable)<br/> |



 

## Notes

The buttons on a toolbar send [**EVENT\_OBJECT\_STATECHANGE**](event-constants.md#event-object-statechange) events.

## Related topics

<dl> <dt>

[IAccessible Interface](/windows/win32/oleacc/nn-oleacc-iaccessible?branch=master)
</dt> </dl>

 

 




