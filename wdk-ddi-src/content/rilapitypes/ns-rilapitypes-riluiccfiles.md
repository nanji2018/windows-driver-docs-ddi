---
UID: NS:rilapitypes.RILUICCFILES
title: RILUICCFILES
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\riluiccfiles_2.htm
old-project: netvista
ms.assetid: 282cd191-03c5-4599-9a61-e84221ef9143
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: RILUICCFILES, RILUICCFILES, *LPRILUICCFILES
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: rilapitypes.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: RILUICCFILES
req.alt-loc: rilapitypes.h
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
req.typenames: RILUICCFILES, *LPRILUICCFILES
req.product: Windows 10 or later.
---

# RILUICCFILES structure



## -description
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code. 



## -syntax

````
typedef struct _RILUICCFILES {
  DWORD               cbSize;
  DWORD               dwNumFiles;
  RILUICCFILEPATH [1] filePath;
} RILUICCFILES, RILUICCFILES;
````


## -struct-fields

### -field cbSize


### -field dwNumFiles


### -field filePath


## -remarks
