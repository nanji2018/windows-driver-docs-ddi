---
UID: NE:wditypes._WDI_BLUETOOTH_COEXISTENCE_SUPPORT
title: _WDI_BLUETOOTH_COEXISTENCE_SUPPORT
author: windows-driver-content
description: The WDI_BLUETOOTH_COEXISTENCE_SUPPORT enumeration defines Bluetooth coexistence support values.
old-location: netvista\wdi_bluetooth_coexistence_support.htm
old-project: netvista
ms.assetid: 88642615-D5DD-4C0E-BAAA-308EB6050E77
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: _WDI_BLUETOOTH_COEXISTENCE_SUPPORT, WDI_BLUETOOTH_COEXISTENCE_SUPPORT
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: wditypes.hpp
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: WDI_BLUETOOTH_COEXISTENCE_SUPPORT
req.alt-loc: wditypes.hpp
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
req.typenames: WDI_BLUETOOTH_COEXISTENCE_SUPPORT
req.product: Windows 10 or later.
---

# _WDI_BLUETOOTH_COEXISTENCE_SUPPORT enumeration



## -description
The WDI_BLUETOOTH_COEXISTENCE_SUPPORT enumeration defines Bluetooth coexistence support values.



## -syntax

````
typedef enum _WDI_BLUETOOTH_COEXISTENCE_SUPPORT { 
  WDI_BLUETOOTH_COEXISTENCE_UNKNOWN                   = 0,
  WDI_BLUETOOTH_COEXISTENCE_PERFORMANCE_MAINTAINED    = 1,
  WDI_BLUETOOTH_COEXISTENCE_WIFI_DEGRADED_TO_1x1      = 2,
  WDI_BLUETOOTH_COEXISTENCE_WIFI_THROUGHPUT_DEGRADED  = 3,
  WDI_BLUETOOTH_COEXISTENCE_MUTUALLY_EXCLUSIVE        = 4
} WDI_BLUETOOTH_COEXISTENCE_SUPPORT;
````


## -enum-fields

### -field WDI_BLUETOOTH_COEXISTENCE_UNKNOWN

Unknown.


### -field WDI_BLUETOOTH_COEXISTENCE_PERFORMANCE_MAINTAINED

Wi-Fi and Bluetooth work at the same performance level during coexistence.


### -field WDI_BLUETOOTH_COEXISTENCE_WIFI_DEGRADED_TO_1x1

Wi-Fi centered. On a 2X2 device, Wi-Fi and Bluetooth coexists. Wi-Fi performance is reduced to 1X1 level.


### -field WDI_BLUETOOTH_COEXISTENCE_WIFI_THROUGHPUT_DEGRADED

Bluetooth centered. When coexisting, Bluetooth has priority and restricts Wi-Fi performance.


### -field WDI_BLUETOOTH_COEXISTENCE_MUTUALLY_EXCLUSIVE

Wi-Fi and Bluetooth are mutually exclusive. One of the two stops working.


## -remarks
