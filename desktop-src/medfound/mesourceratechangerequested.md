---
Description: Raised by a media source to request a new playback rate. The application should call IMFRateControlSetRate with the requested rate. A media source might raise this event if it cannot continue playback at the current rate.
ms.assetid: 705e5a79-836b-417b-a7ed-c733572f6905
title: MESourceRateChangeRequested event
ms.date: 05/31/2018
ms.topic: article
ms.author: windowssdkdev
ms.prod: windows
ms.technology: desktop
---

# MESourceRateChangeRequested event

Raised by a media source to request a new playback rate. The application should call [**IMFRateControl::SetRate**](/windows/win32/mfidl/nf-mfidl-imfratecontrol-setrate?branch=master) with the requested rate. A media source might raise this event if it cannot continue playback at the current rate.

## Event values

Possible values retrieved from [**IMFMediaEvent::GetValue**](/windows/win32/mfobjects/nf-mfobjects-imfmediaevent-getvalue?branch=master) include the following.



| VARTYPE           | Description                                             |
|-------------------|---------------------------------------------------------|
| VT\_R4<br/> | The requested new playback rate.<br/> <br/> |



## Attributes

The following attributes are defined for this event.



| Attribute                                                                    | Description                                                                       |
|------------------------------------------------------------------------------|-----------------------------------------------------------------------------------|
| [**MF\_EVENT\_DO\_THINNING**](mf-event-do-thinning-attribute.md)<br/> | Specifies whether the media source also requests thinning.<br/> <br/> |



## Requirements



|                                     |                                                                                                          |
|-------------------------------------|----------------------------------------------------------------------------------------------------------|
| Minimum supported client<br/> | Windows Vista \[desktop apps only\]<br/>                                                           |
| Minimum supported server<br/> | Windows Server 2008 \[desktop apps only\]<br/>                                                     |
| Header<br/>                   | <dl> <dt>Mfobjects.h (include Mfidl.h)</dt> </dl> |



## See also

<dl> <dt>

[Media Foundation Events](media-foundation-events.md)
</dt> </dl>

 

 



