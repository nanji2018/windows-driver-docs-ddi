---
UID: NF:sercx.SERCX2_PIO_TRANSMIT_CONFIG_INIT
title: SERCX2_PIO_TRANSMIT_CONFIG_INIT function
author: windows-driver-content
description: The SERCX2_PIO_TRANSMIT_CONFIG_INIT function initializes a SERCX2_PIO_TRANSMIT_CONFIG structure.
old-location: serports\sercx2_pio_transmit_config_init.htm
old-project: serports
ms.assetid: B168C2EE-8D27-4A36-8B7F-C8EE719BFAC0
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: SERCX2_PIO_TRANSMIT_CONFIG_INIT
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: sercx.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: Available starting with Windows 8.1.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: SERCX2_PIO_TRANSMIT_CONFIG_INIT
req.alt-loc: 2.0\Sercx.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: Any level.
req.typenames: SERCX_STATUS, *PSERCX_STATUS
req.product: Windows 10 or later.
---

# SERCX2_PIO_TRANSMIT_CONFIG_INIT function



## -description
The <b>SERCX2_PIO_TRANSMIT_CONFIG_INIT</b> function initializes a <a href="..\sercx\ns-sercx-_sercx2_pio_transmit_config.md">SERCX2_PIO_TRANSMIT_CONFIG</a> structure.



## -syntax

````
VOID SERCX2_PIO_TRANSMIT_CONFIG_INIT(
  _Out_ SERCX2_PIO_TRANSMIT_CONFIG                        *PioTransmitConfig,
  _In_  PFN_SERCX2_PIO_TRANSMIT_WRITE_BUFFER              EvtSerCx2PioTransmitWriteBuffer,
  _In_  PFN_SERCX2_PIO_TRANSMIT_ENABLE_READY_NOTIFICATION EvtSerCx2PioTransmitEnableReadyNotification,
  _In_  PFN_SERCX2_PIO_TRANSMIT_CANCEL_READY_NOTIFICATION EvtSerCx2PioTransmitCancelReadyNotification
);
````


## -parameters

### -param PioTransmitConfig [out]

A pointer to the <a href="..\sercx\ns-sercx-_sercx2_pio_transmit_config.md">SERCX2_PIO_TRANSMIT_CONFIG</a> structure that is to be initialized.


### -param EvtSerCx2PioTransmitWriteBuffer [in]

The value to load into the <b>EvtSerCx2PioTransmitWriteBuffer</b> member of the <b>SERCX2_PIO_TRANSMIT_CONFIG</b> structure. For more information, see the description of this member in <a href="..\sercx\ns-sercx-_sercx2_pio_transmit_config.md">SERCX2_PIO_TRANSMIT_CONFIG</a>.


### -param EvtSerCx2PioTransmitEnableReadyNotification [in]

The value to load into the <b>EvtSerCx2PioTransmitEnableReadyNotification</b> member of the <b>SERCX2_PIO_TRANSMIT_CONFIG</b> structure. For more information, see the description of this member in <a href="..\sercx\ns-sercx-_sercx2_pio_transmit_config.md">SERCX2_PIO_TRANSMIT_CONFIG</a>.


### -param EvtSerCx2PioTransmitCancelReadyNotification [in]

The value to load into the <b>EvtSerCx2PioTransmitCancelReadyNotification</b> member of the <b>SERCX2_PIO_TRANSMIT_CONFIG</b> structure. For more information, see the description of this member in <a href="..\sercx\ns-sercx-_sercx2_pio_transmit_config.md">SERCX2_PIO_TRANSMIT_CONFIG</a>.


## -returns
None.


## -remarks
Your serial controller driver must use this function to initialize a <a href="..\sercx\ns-sercx-_sercx2_pio_transmit_config.md">SERCX2_PIO_TRANSMIT_CONFIG</a> structure before passing a pointer to this structure as an input parameter to the <a href="..\sercx\nf-sercx-sercx2piotransmitcreate.md">SerCx2PioTransmitCreate</a> method.

<b>SERCX2_PIO_TRANSMIT_CONFIG_INIT</b> sets the <b>Size</b> member of the structure to <b>sizeof</b>(<b>SERCX2_PIO_TRANSMIT_CONFIG</b>), and sets three additional members of the structure to the values supplied as input parameters to the function. The function sets the other members of the structure to zero. The driver can, if necessary, explicitly set these other members to nonzero values after the <b>SERCX2_PIO_TRANSMIT_CONFIG_INIT</b> call.


## -see-also
<dl>
<dt>
<a href="..\sercx\ns-sercx-_sercx2_pio_transmit_config.md">SERCX2_PIO_TRANSMIT_CONFIG</a>
</dt>
<dt>
<a href="..\sercx\nf-sercx-sercx2piotransmitcreate.md">SerCx2PioTransmitCreate</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [serports\serports]:%20SERCX2_PIO_TRANSMIT_CONFIG_INIT function%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

