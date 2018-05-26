---
title: CB\_GETEDITSEL message
description: Gets the starting and ending character positions of the current selection in the edit control of a combo box.
ms.assetid: 72b64135-e35a-4f72-9fc7-e6bedf495f23
keywords:
- CB_GETEDITSEL message Windows Controls
topic_type:
- apiref
api_name:
- CB_GETEDITSEL
api_location:
- Winuser.h
api_type:
- HeaderDef
ms.date: 05/31/2018
ms.topic: article
ms.author: windowssdkdev
ms.prod: windows
ms.technology: desktop
---

# CB\_GETEDITSEL message

Gets the starting and ending character positions of the current selection in the edit control of a combo box.

## Parameters

<dl> <dt>

*wParam* 
</dt> <dd>

A pointer to a **DWORD** value that receives the starting position of the selection. This parameter can be **NULL**.

</dd> <dt>

*lParam* 
</dt> <dd>

A pointer to a **DWORD** value that receives the ending position of the selection. This parameter can be **NULL**.

</dd> </dl>

## Return value

The return value is a zero-based **DWORD** value with the starting position of the selection in the [**LOWORD**](https://msdn.microsoft.com/library/windows/desktop/ms632659) and with the ending position of the first character after the last selected character in the [**HIWORD**](https://msdn.microsoft.com/library/windows/desktop/ms632657).

## Examples

The following code example shows two ways of retrieving the current selection range.


```C++
DWORD start, end;

// Get the range from [out] parameters.
// hwnd is the handle of the combo box control.
SendMessage(hwnd, CB_GETEDITSEL, (WPARAM)&amp;start, (LPARAM)&amp;end;

// Get the range from the return value.
DWORD range = SendMessage(hwnd, CB_GETEDITSEL, NULL, NULL);
start = LOWORD(range);
end = HIWORD(range);
```



## Requirements



|                                     |                                                                                                          |
|-------------------------------------|----------------------------------------------------------------------------------------------------------|
| Minimum supported client<br/> | Windows Vista \[desktop apps only\]<br/>                                                           |
| Minimum supported server<br/> | Windows Server 2003 \[desktop apps only\]<br/>                                                     |
| Header<br/>                   | <dl> <dt>Winuser.h (include Windows.h)</dt> </dl> |



## See also

<dl> <dt>

**Reference**
</dt> <dt>

[**CB\_SETEDITSEL**](cb-seteditsel.md)
</dt> <dt>

**Other Resources**
</dt> <dt>

[**HIWORD**](https://msdn.microsoft.com/library/windows/desktop/ms632657)
</dt> <dt>

[**LOWORD**](https://msdn.microsoft.com/library/windows/desktop/ms632659)
</dt> </dl>

 

 




