---
UID: NS:ks.KSPROPERTY_STEPPING_LONGLONG
title: KSPROPERTY_STEPPING_LONGLONG
author: windows-driver-content
description: The KSPROPERTY_STEPPING_LONGLONG structure defines the valid range of values for a 64-bit property.
old-location: stream\ksproperty_stepping_longlong.htm
old-project: stream
ms.assetid: 14ec504e-baf6-441a-b908-2d8c051dd45a
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: KSPROPERTY_STEPPING_LONGLONG, KSPROPERTY_STEPPING_LONGLONG, *PKSPROPERTY_STEPPING_LONGLONG
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ks.h
req.include-header: Ks.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: KSPROPERTY_STEPPING_LONGLONG
req.alt-loc: ks.h
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
req.typenames: KSPROPERTY_STEPPING_LONGLONG, *PKSPROPERTY_STEPPING_LONGLONG
---

# KSPROPERTY_STEPPING_LONGLONG structure



## -description
The KSPROPERTY_STEPPING_LONGLONG structure defines the valid range of values for a 64-bit property.



## -syntax

````
typedef struct {
  DWORDLONG                  SteppingDelta;
  KSPROPERTY_BOUNDS_LONGLONG Bounds;
} KSPROPERTY_STEPPING_LONGLONG, *PKSPROPERTY_STEPPING_LONGLONG;
````


## -struct-fields

### -field SteppingDelta

Specifies the step value that should be used to create legal values within the range defined in <b>Bounds</b>.


### -field Bounds

Specifies a structure of type <a href="..\ks\ns-ks-ksproperty_bounds_longlong.md">KSPROPERTY_BOUNDS_LONGLONG</a> that specifies the range of values over which the <b>SteppingDelta</b> is valid.


## -remarks
The <a href="..\ks\ns-ks-ksproperty_memberslist.md">KSPROPERTY_MEMBERSLIST</a> structure may contain structures of this type in its <b>Members</b> array.


## -see-also
<dl>
<dt>
<a href="..\ks\ns-ks-ksproperty_bounds_longlong.md">KSPROPERTY_BOUNDS_LONGLONG</a>
</dt>
<dt>
<a href="..\ks\ns-ks-ksproperty_memberslist.md">KSPROPERTY_MEMBERSLIST</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KSPROPERTY_STEPPING_LONGLONG structure%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

