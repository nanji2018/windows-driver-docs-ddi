---
UID: NF:procgrp.WdmlibProcgrpInitialize
title: WdmlibProcgrpInitialize function
author: windows-driver-content
description: The WdmlibProcgrpInitialize function initializes the Processor Group (ProcGrp) compatibility library.
old-location: kernel\wdmlibprocgrpinitialize.htm
old-project: kernel
ms.assetid: 760f7bd8-0957-4dd0-b201-64173961cbb2
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: WdmlibProcgrpInitialize
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: procgrp.h
req.include-header: Procgrp.h
req.target-type: Desktop
req.target-min-winverclnt: Compatible with Windows 7, Windows Server 2008 R2, Windows Server 2008, Windows Vista, Windows Server 2003, Windows XP, and Windows 2000.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: WdmlibProcgrpInitialize
req.alt-loc: Procgrp.lib,Procgrp.dll
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Procgrp.lib
req.dll: 
req.irql: PASSIVE_LEVEL
req.typenames: WIDTHTABLE, *PWIDTHTABLE
req.product: Windows 10 or later.
---

# WdmlibProcgrpInitialize function



## -description
The <b>WdmlibProcgrpInitialize</b> function initializes the Processor Group (ProcGrp) compatibility library.



## -syntax

````
VOID WdmlibProcgrpInitialize(void);
````


## -parameters


## -returns
None

None

None


## -remarks
This function initializes the ProcGrp library. Call this function before calling any of the other functions in the ProcGrp library. The library implements wrapper functions that have the same names as the following processor-group <b>Ke<i>Xxx</i></b> routines in Windows 7:


<a href="..\ntddk\nf-ntddk-kegetcurrentprocessornumberex.md">KeGetCurrentProcessorNumberEx</a>



<a href="..\ntifs\nf-ntifs-kegetprocessorindexfromnumber.md">KeGetProcessorIndexFromNumber</a>



<a href="..\wdm\nf-wdm-kegetprocessornumberfromindex.md">KeGetProcessorNumberFromIndex</a>



<a href="..\ntddk\nf-ntddk-kequeryactivegroupcount.md">KeQueryActiveGroupCount</a>



<a href="..\ntddk\nf-ntddk-kequeryactiveprocessorcountex.md">KeQueryActiveProcessorCountEx</a>



<a href="..\ntddk\nf-ntddk-kequerygroupaffinity.md">KeQueryGroupAffinity</a>



<a href="..\wdm\nf-wdm-kequerymaximumprocessorcount.md">KeQueryMaximumProcessorCount</a>



<a href="..\ntddk\nf-ntddk-kequerymaximumprocessorcountex.md">KeQueryMaximumProcessorCountEx</a>



<a href="..\ntddk\nf-ntddk-kequerymaximumgroupcount.md">KeQueryMaximumGroupCount</a>



<a href="..\wdm\nf-wdm-kesetsystemaffinitythreadex.md">KeSetSystemAffinityThreadEx</a>



<a href="..\wdm\nf-wdm-kesetsystemgroupaffinitythread.md">KeSetSystemGroupAffinityThread</a>



<a href="..\wdm\nf-wdm-kereverttouseraffinitythreadex.md">KeRevertToUserAffinityThreadEx</a>



<a href="..\wdm\nf-wdm-kereverttousergroupaffinitythread.md">KeRevertToUserGroupAffinityThread</a>



<a href="..\wdm\nf-wdm-kesettargetprocessordpcex.md">KeSetTargetProcessorDpcEx</a>


For more information about the ProcGrp library, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff559909">Processor Group Compatibility Library</a>. </p>