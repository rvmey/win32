---
Description: Allows the callback object to add buttons to the toolbar. Used by IShellFolderViewCBMessageSFVCB.
title: SFVM\_GETBUTTONINFO message
ms.date: 05/31/2018
ms.topic: article
ms.author: windowssdkdev
ms.prod: windows
ms.technology: desktop
---

# SFVM\_GETBUTTONINFO message

Allows the callback object to add buttons to the toolbar. Used by [**IShellFolderViewCB::MessageSFVCB**](/windows/win32/Shlobj/?branch=master).


```C++
SFVM_GETBUTTONINFO 

    lParam = (LPARAM)(LPTBINFO) ptbinfo;

            
```



## Parameters

<dl> <dt>

*ptbinfo* \[out\]
</dt> <dd>

The address of a [**TBINFO**](/windows/win32/Shlobj/ns-shlobj-_tbinfo?branch=master) structure that specifies the number of buttons and how they are to be added to the toolbar.

</dd> </dl>

## Remarks

Buttons can be appended or prepended to the standard system folder view object buttons, or be displayed in place of the standard buttons. This message is followed by a [**SFVM\_GETBUTTONS**](sfvm-getbuttons.md) message that retrieves the information concerning the button specifics.

## Requirements



|                                     |                                                                                     |
|-------------------------------------|-------------------------------------------------------------------------------------|
| Minimum supported client<br/> | Windows 2000 Professional \[desktop apps only\]<br/>                          |
| Minimum supported server<br/> | Windows 2000 Server \[desktop apps only\]<br/>                                |
| Header<br/>                   | <dl> <dt>Shlobj.h</dt> </dl> |



 

 



