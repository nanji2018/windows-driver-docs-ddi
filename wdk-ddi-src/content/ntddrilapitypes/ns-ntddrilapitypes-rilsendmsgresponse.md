---
UID: NS:ntddrilapitypes.RILSENDMSGRESPONSE
title: RILSENDMSGRESPONSE
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilsendmsgresponse.htm
old-project: netvista
ms.assetid: 64ff0ba7-726e-49ee-bb7c-338b77458fc1
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: RILSENDMSGRESPONSE, RILSENDMSGRESPONSE, *LPRILSENDMSGRESPONSE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntddrilapitypes.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: RILSENDMSGRESPONSE
req.alt-loc: ntddrilapitypes.h
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
req.typenames: RILSENDMSGRESPONSE, *LPRILSENDMSGRESPONSE
---

# RILSENDMSGRESPONSE structure



## -description
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.



## -syntax

````
typedef struct _RILSENDMSGRESPONSE {
  DWORD    cbSize;
  DWORD    dwParams;
  HRESULT  hrReturn;
  DWORD    dwCDMACauseCode;
  DWORD    dwCDMAErrorClass;
  DWORD    dwGWLTransportCode;
  DWORD    dwGWLRelayCode;
  DWORD    dwMsgID;
} RILSENDMSGRESPONSE, RILSENDMSGRESPONSE;
````


## -struct-fields

### -field cbSize


### -field dwParams


### -field hrReturn


### -field dwCDMACauseCode


### -field dwCDMAErrorClass


### -field dwGWLTransportCode


### -field dwGWLRelayCode


### -field dwMsgID


## -remarks
