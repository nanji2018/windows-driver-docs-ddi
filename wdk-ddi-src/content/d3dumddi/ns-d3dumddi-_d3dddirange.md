---
UID: NS:d3dumddi._D3DDDIRANGE
title: _D3DDDIRANGE
author: windows-driver-content
description: Specifies a range of memory within a buffer.
old-location: display\d3dddirange.htm
old-project: display
ms.assetid: 3A64DB04-EDAE-419C-947B-67201ECA8068
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: _D3DDDIRANGE, D3DDDIRANGE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Windows
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: Windows Server 2012
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: D3DDDIRANGE
req.alt-loc: D3dumddi.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
req.typenames: D3DDDIRANGE
---

# _D3DDDIRANGE structure



## -description
Specifies a range of memory within a buffer.



## -syntax

````
typedef struct _D3DDDIRANGE {
  UINT Offset;
  UINT Size;
} D3DDDIRANGE;
````


## -struct-fields

### -field Offset

An offset, in bytes, from the start of the buffer.


### -field Size

The size, in bytes, of a block of memory that begins at the buffer location specified by the <b>Offset</b> member.


## -remarks
