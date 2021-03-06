---
UID: NS:ksmedia._KSAUDIO_PACKETSIZE_CONSTRAINTS2
title: _KSAUDIO_PACKETSIZE_CONSTRAINTS2
author: windows-driver-content
description: The KSAUDIO_PACKETSIZE_CONSTRAINTS2 structure describes the physical hardware constraints.
old-location: audio\ksaudio_packetsize_constraints2.htm
old-project: audio
ms.assetid: E87C7AA7-A48A-4569-ADD5-9DC143F919B6
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: _KSAUDIO_PACKETSIZE_CONSTRAINTS2, KSAUDIO_PACKETSIZE_CONSTRAINTS2
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ksmedia.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: KSAUDIO_PACKETSIZE_CONSTRAINTS2
req.alt-loc: ksmedia.h
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
req.typenames: KSAUDIO_PACKETSIZE_CONSTRAINTS2
---

# _KSAUDIO_PACKETSIZE_CONSTRAINTS2 structure



## -description
The <b>KSAUDIO_PACKETSIZE_CONSTRAINTS2</b> structure describes the physical hardware constraints. It includes an array of 0 or more <a href="..\ksmedia\ns-ksmedia-_ksaudio_packetsize_signalprocessingmode_constraint.md">KSAUDIO_PACKETSIZE_PROCESSINGMODE_CONSTRAINT</a> structures describing constraints specific to any signal processing modes.
The driver sets this property before calling <a href="..\portcls\nf-portcls-pcregistersubdevice.md">PcRegisterSubdevice</a> or otherwise enabling its KS filter interface for its streaming pins.



## -syntax

````
typedef struct _KSAUDIO_PACKETSIZE_CONSTRAINTS2 {
  ULONG                                                                                   MinPacketPeriodInHns;
  ULONG                                                                                   PacketSizeFileAlignment;
  ULONG                                                                                   MaxPacketSizeInBytes;
  ULONG                                                                                   NumProcessingModeConstraints;
  _Field_size_(NumProcessingModeConstraints) KSAUDIO_PACKETSIZE_PROCESSINGMODE_CONSTRAINT ProcessingModeConstraints[ANYSIZE_ARRAY];
} KSAUDIO_PACKETSIZE_CONSTRAINTS2, *PKSAUDIO_PACKETSIZE_CONSTRAINTS2;
````


## -struct-fields

### -field MinPacketPeriodInHns

The absolute minimum processing period supported by the driver expressed in hundred-nanosecond (HNS) units. This value can be 0 if the driver has no specific minimum processing period.


### -field PacketSizeFileAlignment

<dl><a id="FILE_BYTE_ALIGNMENT"></a><a id="file_byte_alignment"></a>
<a id="FILE_WORD_ALIGNMENT"></a><a id="file_word_alignment"></a>
<a id="FILE_LONG_ALIGNMENT"></a><a id="file_long_alignment"></a>
<a id="FILE_QUAD_ALIGNMENT"></a><a id="file_quad_alignment"></a>
<a id="FILE_OCTA_ALIGNMENT"></a><a id="file_octa_alignment"></a>
<a id="FILE_32_BYTE_ALIGNMENT"></a><a id="file_32_byte_alignment"></a>
<a id="FILE_64_BYTE_ALIGNMENT"></a><a id="file_64_byte_alignment"></a>
<a id="FILE_128_BYTE_ALIGNMENT"></a><a id="file_128_byte_alignment"></a>
<a id="FILE_256_BYTE_ALIGNMENT"></a><a id="file_256_byte_alignment"></a>
<a id="FILE_512_BYTE_ALIGNMENT"></a><a id="file_512_byte_alignment"></a>


### -field MaxPacketSizeInBytes

The absolute maximum packet size supported by the driver in bytes. This can be zero if the driver has no specific maximum packet size. This size should at least be large enough to support 10 ms buffer of any format supported by the pin. This size should also be greater or equal to MinPacketSize constraints. 



### -field NumProcessingModeConstraints

The number of additional constraints for specific processing modes. This value can be 0.


### -field ProcessingModeConstraints

An array of 0 or more processing mode constraints. 



## -remarks
The driver sets this variable length data structure as the value of the DEVPKEY_KsAudio_PacketSize_Constraints2 property on the PnP interface of the KS filter that has the streaming pins with the constraints. 


For WaveRT drivers, this data structure describes the constraints for a WaveRT packet. Several WaveRT packets (typically 2) are concatenated to form the WaveRT buffer.

The <b>KSAUDIO_PACKETSIZE_CONSTRAINTS2</b> struct is available  beginning with Windows 10, version 1607.</p>