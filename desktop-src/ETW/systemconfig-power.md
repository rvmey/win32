---
Description: This class is the event type class for power configuration events. The following syntax is simplified from MOF code.
ms.assetid: 7065b0b0-9a1d-4fce-a494-5762d5efb239
title: SystemConfig\_Power class
ms.date: 05/31/2018
ms.topic: article
ms.author: windowssdkdev
ms.prod: windows
ms.technology: desktop
---

# SystemConfig\_Power class

This class is the event type class for power configuration events.

The following syntax is simplified from MOF code.

## Syntax

``` syntax
[EventType(16), EventTypeName("Power")]
class SystemConfig_Power : SystemConfig
{
  uint8 s1;
  uint8 s2;
  uint8 s3;
  uint8 s4;
  uint8 s5;
  uint8 Pad1;
  uint8 Pad2;
  uint8 Pad3;
};
```

## Members

The **SystemConfig\_Power** class has these types of members:

-   [Properties](#properties)

### Properties

The **SystemConfig\_Power** class has these properties.

<dl> <dt>

Pad1
</dt> <dd> <dl> <dt>

Data type: **uint8**
</dt> <dt>

Access type: Read-only
</dt> <dt>

Qualifiers: WmiDataId(6)
</dt> </dl>

Not used.

</dd> <dt>

Pad2
</dt> <dd> <dl> <dt>

Data type: **uint8**
</dt> <dt>

Access type: Read-only
</dt> <dt>

Qualifiers: WmiDataId(7)
</dt> </dl>

Not used.

</dd> <dt>

Pad3
</dt> <dd> <dl> <dt>

Data type: **uint8**
</dt> <dt>

Access type: Read-only
</dt> <dt>

Qualifiers: WmiDataId(8)
</dt> </dl>

Not used.

</dd> <dt>

s1
</dt> <dd> <dl> <dt>

Data type: **uint8**
</dt> <dt>

Access type: Read-only
</dt> <dt>

Qualifiers: WmiDataId(1)
</dt> </dl>

True indicates the system supports sleep state S1.

</dd> <dt>

s2
</dt> <dd> <dl> <dt>

Data type: **uint8**
</dt> <dt>

Access type: Read-only
</dt> <dt>

Qualifiers: WmiDataId(2)
</dt> </dl>

True indicates the system supports sleep state S2.

</dd> <dt>

s3
</dt> <dd> <dl> <dt>

Data type: **uint8**
</dt> <dt>

Access type: Read-only
</dt> <dt>

Qualifiers: WmiDataId(3)
</dt> </dl>

True indicates the system supports sleep state S3.

</dd> <dt>

s4
</dt> <dd> <dl> <dt>

Data type: **uint8**
</dt> <dt>

Access type: Read-only
</dt> <dt>

Qualifiers: WmiDataId(4)
</dt> </dl>

True indicates the system supports sleep state S4.

</dd> <dt>

s5
</dt> <dd> <dl> <dt>

Data type: **uint8**
</dt> <dt>

Access type: Read-only
</dt> <dt>

Qualifiers: WmiDataId(5)
</dt> </dl>

True indicates the system supports sleep state S5.

</dd> </dl>

## Requirements



|                                     |                                                      |
|-------------------------------------|------------------------------------------------------|
| Minimum supported client<br/> | Windows Vista \[desktop apps only\]<br/>       |
| Minimum supported server<br/> | Windows Server 2008 \[desktop apps only\]<br/> |



## See also

<dl> <dt>

[**SystemConfig**](systemconfig.md)
</dt> </dl>

 

 



