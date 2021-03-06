---
UID: NS:bthioctl._BTH_SDP_CONNECT
title: _BTH_SDP_CONNECT
author: windows-driver-content
description: The BTH_SDP_CONNECT structure contains input and output information about a connection between the local Bluetooth system and a remote SDP server. This structure is passed as the input buffer and output buffer of IOCTL_BTH_SDP_CONNECT.
old-location: bltooth\bth_sdp_connect.htm
old-project: bltooth
ms.assetid: 328dca02-9276-4a3d-acac-e00721863243
ms.author: windowsdriverdev
ms.date: 12/21/2017
ms.keywords: _BTH_SDP_CONNECT, *PBTH_SDP_CONNECT, BTH_SDP_CONNECT
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: bthioctl.h
req.include-header: Bthioctl.h
req.target-type: Windows
req.target-min-winverclnt: Versions: Supported in Windows Vista, and later.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: BTH_SDP_CONNECT
req.alt-loc: bthioctl.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: <= PASSIVE_LEVEL
req.typenames: *PBTH_SDP_CONNECT, BTH_SDP_CONNECT
---

# _BTH_SDP_CONNECT structure



## -description
The BTH_SDP_CONNECT structure contains input and output information about a connection between the
  local Bluetooth system and a remote SDP server. This structure is passed as the input buffer and output
  buffer of 
  <a href="..\bthioctl\ni-bthioctl-ioctl_bth_sdp_connect.md">IOCTL_BTH_SDP_CONNECT</a>.



## -syntax

````
typedef struct _BTH_SDP_CONNECT {
  BTH_ADDR   bthAddress;
  ULONG      fSdpConnect;
  HANDLE_SDP hConnection;
  UCHAR      requestTimeout;
} BTH_SDP_CONNECT, *PBTH_SDP_CONNECT;
````


## -struct-fields

### -field bthAddress

The address of the remote SDP server that the local system connects to. This address cannot be to
     the local radio.


### -field fSdpConnect

A flag or combination of flags that determines how to handle the connection request. Valid flag
     values are listed in the following table.
     

<table>
<tr>
<th>Flag</th>
<th>Description</th>
</tr>
<tr>
<td>
SDP_CONNECT_ALLOW_PIN

</td>
<td>
If requested, perform a pin exchange with the remote device.

</td>
</tr>
<tr>
<td>
SDP_CONNECT_CACHE

</td>
<td>
Requests are serviced out of the local cache of the SDP record.

</td>
</tr>
</table>
 


### -field hConnection

A handle for the SDP connection on the remote server.


### -field requestTimeout

The timeout, in seconds, for requests to the SDP connection handle that is returned in the 
     <b>hConnection</b> member. If the request times out, the SDP connection returned in 
     <b>hConnection</b> must be closed. The values for this field are bound by SDP_REQUEST_TO_MIN and
     SDP_REQUEST_TO_MAX. If SDP_REQUEST_TO_DEFAULT is specified, the timeout is 30 seconds.


## -remarks


## -see-also
<dl>
<dt>
<a href="..\bthioctl\ni-bthioctl-ioctl_bth_sdp_connect.md">IOCTL_BTH_SDP_CONNECT</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [bltooth\bltooth]:%20BTH_SDP_CONNECT structure%20 RELEASE:%20(12/21/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

