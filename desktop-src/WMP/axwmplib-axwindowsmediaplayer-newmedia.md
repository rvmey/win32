---
title: AxWindowsMediaPlayer.newMedia method
description: The newMedia method returns an IWMPMedia interface for a new media item.
ms.assetid: d10a517e-b4da-4f0b-9d51-9d387578d7dd
keywords:
- newMedia method Windows Media Player
- newMedia method Windows Media Player , AxWindowsMediaPlayer class
- AxWindowsMediaPlayer class Windows Media Player , newMedia method
topic_type:
- apiref
api_name:
- AxWindowsMediaPlayer.newMedia
api_location:
- AxInterop.WMPLib.dll
api_type:
- COM
ms.date: 05/31/2018
ms.topic: article
ms.author: windowssdkdev
ms.prod: windows
ms.technology: desktop
---

# AxWindowsMediaPlayer.newMedia method

The newMedia method returns an IWMPMedia interface for a new media item.

## Syntax


```CSharp
public IWMPMedia newMedia(
  System.String bstrURL
);
```

<span codelanguage="VisualBasic"></span>

<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<thead>
<tr class="header">
<th>VB</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><pre><code>Public Function newMedia( _
  ByVal bstrURL As System.String _
) As IWMPMedia</code></pre></td>
</tr>
</tbody>
</table>



## Parameters

<dl> <dt>

*bstrURL* 
</dt> <dd>

A **System.String** that is the URL of the digital media file that is used to initialize the new media item.

</dd> </dl>

## Return value

A WMPLib.IWMPMedia interface that represents the newly created media item.

## Remarks

The *bstrURL* parameter must not be a zero-length string ("") or null.

## Requirements



|                      |                                                                                                                            |
|----------------------|----------------------------------------------------------------------------------------------------------------------------|
| Version<br/>   | Windows Media Player 9 Series or later<br/>                                                                          |
| Namespace<br/> | **AxWMPLib**<br/>                                                                                                    |
| Assembly<br/>  | <dl> <dt>AxInterop.WMPLib.dll (AxInterop.WMPLib.dll.dll)</dt> </dl> |



## See also

<dl> <dt>

[**AxWindowsMediaPlayer Object (VB and C#)**](axwindowsmediaplayer-object--vb-and-c.md)
</dt> <dt>

[**IWMPMedia Interface (VB and C#)**](iwmpmedia--vb-and-c.md)
</dt> </dl>

 

 




