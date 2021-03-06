---
UID: NS:d3dumddi._D3DDDIARG_DECODEBEGINFRAME
title: _D3DDDIARG_DECODEBEGINFRAME
author: windows-driver-content
description: The D3DDDIARG_DECODEBEGINFRAME structure specifies the Microsoft DirectX Video Accelerator (VA) decoder that should start decoding a frame.
old-location: display\d3dddiarg_decodebeginframe.htm
old-project: display
ms.assetid: 8219beee-b27c-4f81-aef7-8d38363d4645
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: _D3DDDIARG_DECODEBEGINFRAME, D3DDDIARG_DECODEBEGINFRAME
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: D3DDDIARG_DECODEBEGINFRAME
req.alt-loc: d3dumddi.h
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
req.typenames: D3DDDIARG_DECODEBEGINFRAME
---

# _D3DDDIARG_DECODEBEGINFRAME structure



## -description
The D3DDDIARG_DECODEBEGINFRAME structure specifies the Microsoft DirectX Video Accelerator (VA) decoder that should start decoding a frame. 



## -syntax

````
typedef struct _D3DDDIARG_DECODEBEGINFRAME {
  HANDLE             hDecode;
  DXVADDI_PVP_SETKEY *pPVPSetKey;
} D3DDDIARG_DECODEBEGINFRAME;
````


## -struct-fields

### -field hDecode

A handle to the DirectX VA decode device. The user-mode display driver returns this handle in a call to its <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_createdecodedevice.md">CreateDecodeDevice</a> function.


### -field pPVPSetKey

A pointer to the <a href="..\d3dumddi\ns-d3dumddi-_dxvaddi_pvp_setkey.md">DXVADDI_PVP_SETKEY</a> structure that contains a key that the driver requires for the decode device to start operating. 


## -remarks


## -see-also
<dl>
<dt>
<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_createdecodedevice.md">CreateDecodeDevice</a>
</dt>
<dt>
<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_decodebeginframe.md">DecodeBeginFrame</a>
</dt>
<dt>
<a href="..\d3dumddi\ns-d3dumddi-_dxvaddi_pvp_setkey.md">DXVADDI_PVP_SETKEY</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DDDIARG_DECODEBEGINFRAME structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

