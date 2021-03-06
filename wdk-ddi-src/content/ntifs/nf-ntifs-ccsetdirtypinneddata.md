---
UID: NF:ntifs.CcSetDirtyPinnedData
title: CcSetDirtyPinnedData function
author: windows-driver-content
description: The CcSetDirtyPinnedData routine marks as dirty the buffer control block (BCB) for a pinned buffer whose contents have been modified.
old-location: ifsk\ccsetdirtypinneddata.htm
old-project: ifsk
ms.assetid: f621a54f-ed40-4ec7-8678-7c72fcd9e704
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: CcSetDirtyPinnedData
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
req.alt-api: CcSetDirtyPinnedData
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

# CcSetDirtyPinnedData function



## -description
The <b>CcSetDirtyPinnedData</b> routine marks as dirty the buffer control block (BCB) for a pinned buffer whose contents have been modified.



## -syntax

````
VOID CcSetDirtyPinnedData(
  _In_     PVOID          BcbVoid,
  _In_opt_ PLARGE_INTEGER Lsn
);
````


## -parameters

### -param BcbVoid [in]

Pointer to the BCB structure to be marked as dirty.


### -param Lsn [in, optional]

Logical sequence number (LSN) to be associated with this buffer.


## -returns
None


## -remarks
<b>CcSetDirtyPinnedData</b> marks the BCB as dirty, so that the contents of the pinned buffer will be lazy-written to disk. Even if the flush operation is to be performed by some means other than the lazy writer, <b>CcSetDirtyPinnedData</b> should be called whenever the contents of a pinned buffer are modified. This is especially important if the buffer was pinned only for read access (by <a href="..\ntifs\nf-ntifs-ccpinread.md">CcPinRead</a> or <a href="..\ntifs\nf-ntifs-ccpinmappeddata.md">CcPinMappedData</a>). Although buffers that are pinned only for read access can be modified, their contents are not automatically flushed to disk unless the buffers have been marked as dirty by calling <b>CcSetDirtyPinnedData</b>.


## -see-also
<dl>
<dt>
<a href="..\ntifs\nf-ntifs-ccmapdata.md">CcMapData</a>
</dt>
<dt>
<a href="..\ntifs\nf-ntifs-ccpinmappeddata.md">CcPinMappedData</a>
</dt>
<dt>
<a href="..\ntifs\nf-ntifs-ccpinread.md">CcPinRead</a>
</dt>
<dt>
<a href="..\ntifs\nf-ntifs-ccpreparepinwrite.md">CcPreparePinWrite</a>
</dt>
<dt>
<a href="..\ntifs\nf-ntifs-ccunpindata.md">CcUnpinData</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20CcSetDirtyPinnedData routine%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

