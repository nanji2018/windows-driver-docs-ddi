---
UID: NS:ntddrilapitypes.RILUICCCARDINFO
title: RILUICCCARDINFO
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\riluicccardinfo.htm
old-project: netvista
ms.assetid: 761f1ab6-75e6-4c40-b79c-01f2e92df495
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: RILUICCCARDINFO, *LPRILUICCCARDINFO, RILUICCCARDINFO
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntddrilapitypes.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: RILUICCCARDINFO
req.alt-loc: ntddrilapitypes.h
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
req.typenames: *LPRILUICCCARDINFO, RILUICCCARDINFO
---

# RILUICCCARDINFO structure



## -description
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.



## -syntax

````
typedef struct _RILUICCCARDINFO {
  DWORD              cbSize;
  DWORD              dwParams;
  BOOL               fIsVirtualCard;
  BYTE [10]          IccId;
  DWORD              dwNumApps;
  RILUICCAPPINFO [1] AppInfo;
} RILUICCCARDINFO, RILUICCCARDINFO;
````


## -struct-fields

### -field cbSize


### -field dwParams


### -field fIsVirtualCard


### -field IccId


### -field dwNumApps


### -field AppInfo


## -remarks
