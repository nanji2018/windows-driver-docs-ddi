---
UID: NF:midatlax.RxDestroyMidAtlas
title: RxDestroyMidAtlas function
author: windows-driver-content
description: RxDestroyMidAtlas destroys an existing instance of a MID_ATLAS data structure and frees the allocated memory.
old-location: ifsk\rxdestroymidatlas.htm
old-project: ifsk
ms.assetid: 9d5c08c8-8306-46e3-b10b-eeefe473d340
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: RxDestroyMidAtlas
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: midatlax.h
req.include-header: Midatlax.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: RxDestroyMidAtlas
req.alt-loc: midatlax.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: <= APC_LEVEL
req.typenames: MCD_INIT_DATA, *PMCD_INIT_DATA
---

# RxDestroyMidAtlas function



## -description
<b>RxDestroyMidAtlas</b> destroys an existing instance of a MID_ATLAS data structure and frees the allocated memory. 



## -syntax

````
VOID RxDestroyMidAtlas(
   PRX_MID_ATLAS       pMidAtlas,
   PCONTEXT_DESTRUCTOR pContextDestructor
);
````


## -parameters

### -param pMidAtlas 

The MID_ATLAS structure to be freed.


### -param pContextDestructor 

An associated context destructor.


## -returns
None 


## -remarks
RDBSS defines a Multiplex ID (MID), a 16-bit value, that can be used by both the network client (mini-redirector) and the server to distinguish between the concurrently active requests on any connection. A MID is part of a MID_ATLAS data structure allocated by calling <b>RxCreateMidAtlas</b>.

<b>RxDestroyMidAtlas</b> destroys a MID_ATLAS data structure previously created by a call to <b>RxCreateMidAtlas</b>. As a side effect, <b>RxDestroyMidAtlas</b> invokes the passed in context destructor on every valid context in the MID_ATLAS. 


## -see-also
<dl>
<dt>
<a href="..\midatlax\nf-midatlax-rxassociatecontextwithmid.md">RxAssociateContextWithMid</a>
</dt>
<dt>
<a href="..\midatlax\nf-midatlax-rxcreatemidatlas.md">RxCreateMidAtlas</a>
</dt>
<dt>
<a href="..\midatlax\nf-midatlax-rxmapmidtocontext.md">RxMapMidToContext</a>
</dt>
<dt>
<a href="..\midatlax\nf-midatlax-rxmapanddissociatemidfromcontext.md">RxMapAndDissociateMidFromContext</a>
</dt>
<dt>
<a href="..\midatlax\nf-midatlax-rxreassociatemid.md">RxReassociateMid</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20RxDestroyMidAtlas function%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

