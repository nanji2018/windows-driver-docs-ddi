---
UID: NF:ntddk.IoSetFileObjectIgnoreSharing
title: IoSetFileObjectIgnoreSharing function
author: windows-driver-content
description: The IoSetFileObjectIgnoreSharing routine sets a file object to ignore file sharing access checks.
old-location: ifsk\iosetfileobjectignoresharing.htm
old-project: ifsk
ms.assetid: 14863379-0639-4D24-AFA4-AE2196328B87
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: IoSetFileObjectIgnoreSharing
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntddk.h
req.include-header: Ntddk.h, Ntifs.h, Fltkernel.h
req.target-type: Universal
req.target-min-winverclnt: This routine is available starting with Windows 7.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IoSetFileObjectIgnoreSharing
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
req.irql: Any
req.typenames: WHEA_RAW_DATA_FORMAT, *PWHEA_RAW_DATA_FORMAT
---

# IoSetFileObjectIgnoreSharing function



## -description
The <b>IoSetFileObjectIgnoreSharing</b> routine sets a file object to ignore file  sharing access checks.



## -syntax

````
NTSTATUS IoSetFileObjectIgnoreSharing(
   PFILE_OBJECT FileObject
);
````


## -parameters

### -param FileObject 

Pointer to a file object for the file.


## -returns
<b>IoSetFileObjectIgnoreSharing</b> returns STATUS_SUCCESS or an appropriate NTSTATUS code such as one of the following: 
<dl>
<dt><b>STATUS_NOT_FOUND</b></dt>
</dl>The option information for <i>FileObject</i> was not found. The status of sharing access checking cannot be set.
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>The option information was not created for <i>FileObject</i>. The status of sharing access checking cannot be set.

 


## -remarks


## -see-also
<dl>
<dt>
<a href="..\ntddk\nf-ntddk-ioisfileobjectignoringsharing.md">IoIsFileObjectIgnoringSharing</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20IoSetFileObjectIgnoreSharing routine%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

