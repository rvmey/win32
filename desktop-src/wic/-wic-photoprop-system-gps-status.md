---
Description: The photo metadata policy for the System.GPS.Status property.
ms.assetid: 74ea0384-3b1f-4d5e-8713-7b3936813a3a
title: System.GPS.Status Photo Metadata Policy
ms.date: 05/31/2018
ms.topic: article
ms.author: windowssdkdev
ms.prod: windows
ms.technology: desktop
---

# System.GPS.Status Photo Metadata Policy

The photo metadata policy for the [System.GPS.Status](http://msdn.microsoft.com/en-us/library/bb760590(VS.85).aspx) property.

### PKEY

PKEY\_GPS\_Status

### Containers

JPEG, TIFF

### Read-Only

No

### Output PROPVARIANT Type

VT\_LPWSTR

### Input PROPVARIANT Type

VT\_LPWSTR is preferred, but VT\_LPSTR is also accepted.

### Conflict Resolution Policy

Values from different schemas are reconciled.

### JPEG Policies

### Read Paths



| Order | Path                     | Disk Format |
|-------|--------------------------|-------------|
| 1     | /app1/ifd/gps/{ushort=9} | ascii       |
| 2     | /xmp/exif:GPSStatus      | unicode     |



 

### Write Paths



| Order | Path                     | Disk Format |
|-------|--------------------------|-------------|
| 1     | /app1/ifd/gps/{ushort=9} | ascii       |
| 2     | /xmp/exif:GPSStatus      | unicode     |



 

### Remove Paths



| Order | Path                     |
|-------|--------------------------|
| 1     | /app1/ifd/gps/{ushort=9} |
| 2     | /xmp/exif:gpsstatus      |



 

### TIFF Policies

### Read Paths



| Order | Path                    | Disk Format |
|-------|-------------------------|-------------|
| 1     | /ifd/gps/{ushort=9}     | ascii       |
| 2     | /ifd/xmp/exif:GPSStatus | unicode     |



 

### Write Paths



| Order | Path                    | Disk Format |
|-------|-------------------------|-------------|
| 1     | /ifd/gps/{ushort=9}     | ascii       |
| 2     | /ifd/xmp/exif:GPSStatus | unicode     |



 

### Remove Paths



| Order | Path                    |
|-------|-------------------------|
| 1     | /ifd/gps/{ushort=9}     |
| 2     | /ifd/xmp/exif:gpsstatus |



 

## Remarks

## Related topics

<dl> <dt>

[System.GPS.Status](http://msdn.microsoft.com/en-us/library/bb760590(VS.85).aspx)
</dt> </dl>

 

 


