---
UID: NF:wdm.READ_PORT_UCHAR
title: READ_PORT_UCHAR function
author: windows-driver-content
description: The READ_PORT_UCHAR routine reads a byte from the specified port address.
old-location: kernel\read_port_uchar.htm
old-project: kernel
ms.assetid: a58e55f5-d657-43bf-afef-05af7c6c02cc
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: READ_PORT_UCHAR
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 2000.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: READ_PORT_UCHAR
req.alt-loc: Hal.lib,Hal.dll
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Hal.lib
req.dll: 
req.irql: Any level (see Remarks section)
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# READ_PORT_UCHAR function



## -description
The <b>READ_PORT_UCHAR</b> routine reads a byte from the specified port address.



## -syntax

````
UCHAR READ_PORT_UCHAR(
  _In_ PUCHAR Port
);
````


## -parameters

### -param Port [in]

Specifies the port address, which must be a mapped memory range in I/O space. 


## -returns
<b>READ_PORT_UCHAR</b> returns the byte that is read from the specified port address.


## -remarks
Callers of <b>READ_PORT_UCHAR</b> can be running at any IRQL, assuming the <i>Port</i> is resident, mapped device memory.</p>