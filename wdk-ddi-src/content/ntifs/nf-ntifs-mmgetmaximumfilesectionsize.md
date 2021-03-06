---
UID: NF:ntifs.MmGetMaximumFileSectionSize
title: MmGetMaximumFileSectionSize function
author: windows-driver-content
description: The MmGetMaximumFileSectionSize returns the maximum possible size of a file section for the current version of Windows.
old-location: ifsk\mmgetmaximumfilesectionsize.htm
old-project: ifsk
ms.assetid: 5B3E5B33-EFED-485A-A62A-7A54322408AC
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: MmGetMaximumFileSectionSize
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: MmGetMaximumFileSectionSize
req.alt-loc: NtosKrnl.exe
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: <= APC_LEVEL
req.typenames: TOKEN_TYPE
---

# MmGetMaximumFileSectionSize function



## -description
The <b>MmGetMaximumFileSectionSize</b> returns the maximum possible size of a file section for the current version of Windows.



## -syntax

````
ULONGLONG MmGetMaximumFileSectionSize(void);
````


## -parameters


## -returns
The maximum file section size supported by the current version of Windows.

The maximum file section size supported by the current version of Windows.

The maximum file section size supported by the current version of Windows.


## -remarks
