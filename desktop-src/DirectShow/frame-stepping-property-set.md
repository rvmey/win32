---
Description: Frame Stepping Property Set
ms.assetid: 01abe1fe-fc2f-44cb-9546-45a8d682a179
title: Frame Stepping Property Set
ms.date: 05/31/2018
ms.topic: article
ms.author: windowssdkdev
ms.prod: windows
ms.technology: desktop
---

# Frame Stepping Property Set

Decoders that implement frame-accurate seeking under Microsoft DirectShow must implement the AM\_KSPROPSETID\_FrameStep property set, which is used in conjunction with the [**IVideoFrameStep**](/windows/win32/Strmif/nn-strmif-ivideoframestep?branch=master) interface.



|                   |                            |
|-------------------|----------------------------|
| Property Set GUID | AM\_KSPROPSETID\_FrameStep |



 



| Property ID                              | Description                                                                                                                                                                     |
|------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| AM\_PROPERTY\_FRAMESTEP\_STEP            | Instructs the decoder to begin a step operation and passes an [**AM\_PROPERTY\_FRAMESTEP**](/windows/win32/amvideo/ns-amvideo-_am_framestep_step?branch=master) structure that specifies the number of steps.            |
| AM\_PROPERTY\_FRAMESTEP\_CANCEL          | Instructs the decoder to cancel the current step operation. No instance data is associated with this property.                                                                  |
| AM\_PROPERTY\_FRAMESTEP\_CANSTEP         | The decoder returns S\_OK on this instruction to indicate that it can perform frame stepping, S\_FALSE otherwise. No instance data is passed when this property is set.         |
| AM\_PROPERTY\_FRAMESTEP\_CANSTEPMULTIPLE | The decoder returns S\_OK on this instruction to indicate that it can step multiple frames at a time, S\_FALSE otherwise. No instance data is passed when this property is set. |



 

## Related topics

<dl> <dt>

[Property Sets](property-sets.md)
</dt> </dl>

 

 


