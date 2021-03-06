---
UID: NS:fwpsk.FWPS_STREAM_DATA_OFFSET0_
title: FWPS_STREAM_DATA_OFFSET0_
author: windows-driver-content
description: The FWPS_STREAM_DATA_OFFSET0 structure defines an offset into a portion of a data stream that is described by an FWPS_STREAM_DATA0 structure.Note  FWPS_STREAM_DATA_OFFSET0 is a specific version of FWPS_STREAM_DATA_OFFSET.
old-location: netvista\fwps_stream_data_offset0.htm
old-project: netvista
ms.assetid: a6b60fa1-23ed-44dd-8300-c66d5f907993
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: FWPS_STREAM_DATA_OFFSET0_, FWPS_STREAM_DATA_OFFSET0
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: fwpsk.h
req.include-header: Fwpsk.h
req.target-type: Windows
req.target-min-winverclnt: Available starting with Windows Vista.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: FWPS_STREAM_DATA_OFFSET0
req.alt-loc: fwpsk.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: <= DISPATCH_LEVEL
req.typenames: FWPS_STREAM_DATA_OFFSET0
---

# FWPS_STREAM_DATA_OFFSET0_ structure



## -description
The <b>FWPS_STREAM_DATA_OFFSET0</b> structure defines an offset into a portion of a data stream that is
  described by an 
  <a href="..\fwpsk\ns-fwpsk-fwps_stream_data0_.md">FWPS_STREAM_DATA0</a> structure.



## -syntax

````
typedef struct FWPS_STREAM_DATA_OFFSET0_ {
  NET_BUFFER_LIST *netBufferList;
  NET_BUFFER      *netBuffer;
  MDL             *mdl;
  UINT32          mdlOffset;
  UINT32          netBufferOffset;
  SIZE_T          streamDataOffset;
} FWPS_STREAM_DATA_OFFSET0;
````


## -struct-fields

### -field netBufferList

A pointer to the 
     <a href="..\ndis\ns-ndis-_net_buffer_list.md">NET_BUFFER_LIST</a> structure in which the
     offset lies.


### -field netBuffer

A pointer to the 
     <a href="..\ndis\ns-ndis-_net_buffer.md">NET_BUFFER</a> structure in which the offset
     lies.


### -field mdl

A pointer to the Memory Descriptor List (MDL) in which the offset lies.


### -field mdlOffset

The byte offset from the beginning of the MDL pointed to by the 
     <b>Mdl</b> member.


### -field netBufferOffset

Reserved for system use. Callout drivers must not use this member.


### -field streamDataOffset

Reserved for system use. Callout drivers must not use this member.


## -remarks
An FWPS_STREAM_DATA_OFFSET0 structure is contained within an 
    <a href="..\fwpsk\ns-fwpsk-fwps_stream_data0_.md">FWPS_STREAM_DATA0</a> structure. The
    FWPS_STREAM_DATA_OFFSET0 structure specifies an offset into the data stream.

The combination of the 
    <b>netBufferList</b>, 
    <b>netBuffer</b>, 
    <b>Mdl</b>, and 
    <b>mdlOffset</b> members provide the location of the first byte of the data of interest.


## -see-also
<dl>
<dt>
<a href="..\fwpsk\ns-fwpsk-fwps_stream_data0_.md">FWPS_STREAM_DATA0</a>
</dt>
<dt>
<a href="..\ndis\ns-ndis-_net_buffer.md">NET_BUFFER</a>
</dt>
<dt>
<a href="..\ndis\ns-ndis-_net_buffer_list.md">NET_BUFFER_LIST</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20FWPS_STREAM_DATA_OFFSET0 structure%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

