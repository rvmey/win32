---
Description: The following are the window class styles.
ms.assetid: BE908D51-25DD-45d0-B6AA-28B4C627715B
title: Window Class Styles
ms.date: 05/31/2018
ms.topic: article
ms.author: windowssdkdev
ms.prod: windows
ms.technology: desktop
---

# Window Class Styles

The following are the window class styles.



| Constant/value                                                                                                                                                                                                                           | Description                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |
|:-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|:--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| <span id="CS_BYTEALIGNCLIENT"></span><span id="cs_bytealignclient"></span><dl> <dt>**CS\_BYTEALIGNCLIENT**</dt> <dt>0x1000</dt> </dl> | Aligns the window's client area on a byte boundary (in the x direction). This style affects the width of the window and its horizontal placement on the display.<br/>                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |
| <span id="CS_BYTEALIGNWINDOW"></span><span id="cs_bytealignwindow"></span><dl> <dt>**CS\_BYTEALIGNWINDOW**</dt> <dt>0x2000</dt> </dl> | Aligns the window on a byte boundary (in the x direction). This style affects the width of the window and its horizontal placement on the display.<br/>                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                               |
| <span id="CS_CLASSDC"></span><span id="cs_classdc"></span><dl> <dt>**CS\_CLASSDC**</dt> <dt>0x0040</dt> </dl>                         | Allocates one device context to be shared by all windows in the class. Because window classes are process specific, it is possible for multiple threads of an application to create a window of the same class. It is also possible for the threads to attempt to use the device context simultaneously. When this happens, the system allows only one thread to successfully finish its drawing operation. <br/>                                                                                                                                                                                                                                                                                                                                                                     |
| <span id="CS_DBLCLKS"></span><span id="cs_dblclks"></span><dl> <dt>**CS\_DBLCLKS**</dt> <dt>0x0008</dt> </dl>                         | Sends a double-click message to the window procedure when the user double-clicks the mouse while the cursor is within a window belonging to the class. <br/>                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                          |
| <span id="CS_DROPSHADOW"></span><span id="cs_dropshadow"></span><dl> <dt>**CS\_DROPSHADOW**</dt> <dt>0x00020000</dt> </dl>            | Enables the drop shadow effect on a window. The effect is turned on and off through **SPI\_SETDROPSHADOW**. Typically, this is enabled for small, short-lived windows such as menus to emphasize their Z-order relationship to other windows. Windows created from a class with this style must be top-level windows; they may not be child windows.<br/>                                                                                                                                                                                                                                                                                                                                                                                                                             |
| <span id="CS_GLOBALCLASS"></span><span id="cs_globalclass"></span><dl> <dt>**CS\_GLOBALCLASS**</dt> <dt>0x4000</dt> </dl>             | Indicates that the window class is an application global class. For more information, see the "Application Global Classes" section of [About Window Classes](about-window-classes.md).<br/>                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                          |
| <span id="CS_HREDRAW"></span><span id="cs_hredraw"></span><dl> <dt>**CS\_HREDRAW**</dt> <dt>0x0002</dt> </dl>                         | Redraws the entire window if a movement or size adjustment changes the width of the client area.<br/>                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |
| <span id="CS_NOCLOSE"></span><span id="cs_noclose"></span><dl> <dt>**CS\_NOCLOSE**</dt> <dt>0x0200</dt> </dl>                         | Disables **Close** on the window menu.<br/>                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                           |
| <span id="CS_OWNDC"></span><span id="cs_owndc"></span><dl> <dt>**CS\_OWNDC**</dt> <dt>0x0020</dt> </dl>                               | Allocates a unique device context for each window in the class. <br/>                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |
| <span id="CS_PARENTDC"></span><span id="cs_parentdc"></span><dl> <dt>**CS\_PARENTDC**</dt> <dt>0x0080</dt> </dl>                      | Sets the clipping rectangle of the child window to that of the parent window so that the child can draw on the parent. A window with the **CS\_PARENTDC** style bit receives a regular device context from the system's cache of device contexts. It does not give the child the parent's device context or device context settings. Specifying **CS\_PARENTDC** enhances an application's performance. <br/>                                                                                                                                                                                                                                                                                                                                                                         |
| <span id="CS_SAVEBITS"></span><span id="cs_savebits"></span><dl> <dt>**CS\_SAVEBITS**</dt> <dt>0x0800</dt> </dl>                      | Saves, as a bitmap, the portion of the screen image obscured by a window of this class. When the window is removed, the system uses the saved bitmap to restore the screen image, including other windows that were obscured. Therefore, the system does not send [**WM\_PAINT**](gdi.wm_paint) messages to windows that were obscured if the memory used by the bitmap has not been discarded and if other screen actions have not invalidated the stored image. <br/> This style is useful for small windows (for example, menus or dialog boxes) that are displayed briefly and then removed before other screen activity takes place. This style increases the time required to display the window, because the system must first allocate memory to store the bitmap.<br/> |
| <span id="CS_VREDRAW"></span><span id="cs_vredraw"></span><dl> <dt>**CS\_VREDRAW**</dt> <dt>0x0001</dt> </dl>                         | Redraws the entire window if a movement or size adjustment changes the height of the client area.<br/>                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                |



## Requirements



|                                     |                                                                                                          |
|-------------------------------------|----------------------------------------------------------------------------------------------------------|
| Minimum supported client<br/> | Windows 2000 Professional \[desktop apps only\]<br/>                                               |
| Minimum supported server<br/> | Windows 2000 Server \[desktop apps only\]<br/>                                                     |
| Header<br/>                   | <dl> <dt>Winuser.h (include Windows.h)</dt> </dl> |



 

 



