---
UID: NI:ntddvdeo.IOCTL_VIDEO_GET_BANK_SELECT_CODE
title: IOCTL_VIDEO_GET_BANK_SELECT_CODE
author: windows-driver-content
description: Returns a block of x86-specific executable code to be used by a high-resolution SVGA display driver for bank switching. Miniport drivers for VGA-compatible adapters are required to support this modal request; optional for other miniport drivers.
old-location: display\ioctl_video_get_bank_select_code.htm
old-project: display
ms.assetid: 2d5f0224-dbed-461b-bf05-4db7ae7d810e
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: _TAPE_WRITE_MARKS, *PTAPE_WRITE_MARKS, TAPE_WRITE_MARKS
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: ioctl
req.header: ntddvdeo.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IOCTL_VIDEO_GET_BANK_SELECT_CODE
req.alt-loc: Ntddvdeo.h
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
req.typenames: *PTAPE_WRITE_MARKS, TAPE_WRITE_MARKS
---

# IOCTL_VIDEO_GET_BANK_SELECT_CODE IOCTL



## -description

Returns a block of x86-specific executable code to be used by a high-resolution SVGA display driver for bank switching. Miniport drivers for VGA-compatible adapters are required to support this modal request; optional for other miniport drivers.



Returns a block of x86-specific executable code to be used by a high-resolution SVGA display driver for bank switching. Miniport drivers for VGA-compatible adapters are required to support this modal request; optional for other miniport drivers.



## -ioctlparameters

### -input-buffer
None


### -input-buffer-length

<text></text>

### -output-buffer
The miniport driver returns a VIDEO_BANK_SELECT structure in the VRP <b>OutputBuffer</b>.


### -output-buffer-length

<text></text>

### -in-out-buffer

<text></text>

### -inout-buffer-length

<text></text>

### -status-block
I/O Status block
If the miniport driver returns its code block, it sets the <b>Information</b> member of the <a href="..\video\ns-video-_status_block.md">STATUS_BLOCK</a> structure to <b>sizeof</b>(VIDEO_BANK_SELECT); otherwise, the miniport driver sets this member to zero.


## -remarks


## -see-also
<dl>
<dt>
<a href="..\video\ns-video-_status_block.md">STATUS_BLOCK</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20IOCTL_VIDEO_GET_BANK_SELECT_CODE control code%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

