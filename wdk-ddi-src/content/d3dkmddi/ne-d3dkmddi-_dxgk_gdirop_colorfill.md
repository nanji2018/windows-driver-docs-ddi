---
UID: NE:d3dkmddi._DXGK_GDIROP_COLORFILL
title: _DXGK_GDIROP_COLORFILL
author: windows-driver-content
description: The DXGK_GDIROP_COLORFILL enumeration indicates the type of GDI raster operation (ROP) to implement in a GDI hardware-accelerated color fill operation.
old-location: display\dxgk_gdirop_colorfill.htm
old-project: display
ms.assetid: 1ef99bb0-855a-46d1-9702-5fc3eba5e68e
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: _DXGK_GDIROP_COLORFILL, DXGK_GDIROP_COLORFILL
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: d3dkmddi.h
req.include-header: D3dkmddi.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows 7 and later versions of the Windows operating systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: DXGK_GDIROP_COLORFILL
req.alt-loc: d3dkmddi.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL
req.typenames: DXGK_GDIROP_COLORFILL
---

# _DXGK_GDIROP_COLORFILL enumeration



## -description
The DXGK_GDIROP_COLORFILL enumeration indicates the type of GDI raster operation (ROP) to implement in a GDI hardware-accelerated color fill operation.



## -syntax

````
typedef enum _DXGK_GDIROP_COLORFILL { 
  DXGK_GDIROPCF_INVALID    = 0,
  DXGK_GDIROPCF_PATCOPY    = 1,
  DXGK_GDIROPCF_PATINVERT  = 2,
  DXGK_GDIROPCF_PDXN       = 3,
  DXGK_GDIROPCF_DSTINVERT  = 4,
  DXGK_GDIROPCF_PATAND     = 5,
  DXGK_GDIROPCF_PATOR      = 6,
  DXGK_GDIROPCF_ROP3       = 7
} DXGK_GDIROP_COLORFILL;
````


## -enum-fields

### -field DXGK_GDIROPCF_INVALID

Indicates that the GDI raster operation is invalid.


### -field DXGK_GDIROPCF_PATCOPY

Indicates that the specified color is copied into all pixels of the destination rectangle.


### -field DXGK_GDIROPCF_PATINVERT

Indicates that the specified color is combined with the colors of the destination rectangle by using the Boolean <b>XOR</b> operator.


### -field DXGK_GDIROPCF_PDXN

Indicates that the specified color is combined with the colors of the destination rectangle by using the Boolean <b>NOT(XOR)</b> operator.


### -field DXGK_GDIROPCF_DSTINVERT

Indicates that the destination rectangle is inverted.


### -field DXGK_GDIROPCF_PATAND

Indicates that the specified color is combined with the colors of the destination rectangle by using the Boolean <b>AND</b> operator.


### -field DXGK_GDIROPCF_PATOR

Indicates that the colors of the specified pattern are combined with the colors of the destination rectangle by using the Boolean <b>OR</b> operator.


### -field DXGK_GDIROPCF_ROP3

Indicates that a ternary GDI raster operation (ROP3) will be applied.


## -remarks
