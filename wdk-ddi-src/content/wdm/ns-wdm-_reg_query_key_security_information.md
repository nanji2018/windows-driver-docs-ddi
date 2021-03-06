---
UID: NS:wdm._REG_QUERY_KEY_SECURITY_INFORMATION
title: _REG_QUERY_KEY_SECURITY_INFORMATION
author: windows-driver-content
description: The REG_QUERY_KEY_SECURITY_INFORMATION structure receives security information for a registry key object.
old-location: kernel\reg_query_key_security_information.htm
old-project: kernel
ms.assetid: 8bfe793d-c902-4459-98eb-e134759efc48
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: _REG_QUERY_KEY_SECURITY_INFORMATION, REG_QUERY_KEY_SECURITY_INFORMATION, *PREG_QUERY_KEY_SECURITY_INFORMATION
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Windows
req.target-min-winverclnt: Available on Windows Vista and later versions of the Windows operating system.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: REG_QUERY_KEY_SECURITY_INFORMATION
req.alt-loc: wdm.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL (see Remarks section)
req.typenames: REG_QUERY_KEY_SECURITY_INFORMATION, *PREG_QUERY_KEY_SECURITY_INFORMATION
req.product: Windows 10 or later.
---

# _REG_QUERY_KEY_SECURITY_INFORMATION structure



## -description
The <b>REG_QUERY_KEY_SECURITY_INFORMATION</b> structure receives security information for a registry key object.



## -syntax

````
typedef struct _REG_QUERY_KEY_SECURITY_INFORMATION {
  PVOID                 Object;
  PSECURITY_INFORMATION SecurityInformation;
  PSECURITY_DESCRIPTOR  SecurityDescriptor;
  PULONG                Length;
  PVOID                 CallContext;
  PVOID                 ObjectContext;
  PVOID                 Reserved;
} REG_QUERY_KEY_SECURITY_INFORMATION, *PREG_QUERY_KEY_SECURITY_INFORMATION;
````


## -struct-fields

### -field Object

A pointer to the registry key object for the key whose security information is being retrieved.


### -field SecurityInformation

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff556635">SECURITY_INFORMATION</a>-typed value that identifies the type of security information that is being requested. 


### -field SecurityDescriptor

A pointer to a <a href="..\ntifs\ns-ntifs-_security_descriptor.md">SECURITY_DESCRIPTOR</a> structure that receives security information for the key object. 


### -field Length

The length, in bytes of the <b>SECURITY_DESCRIPTOR</b> structure that <b>SecurityDescriptor</b> points to.


### -field CallContext

Optional driver-defined context information that the driver's <a href="https://msdn.microsoft.com/library/windows/hardware/ff560903">RegistryCallback</a> routine can supply. This member is defined for Windows Vista and later versions of the Windows operating system. 


### -field ObjectContext

A pointer to driver-defined context information that the driver has associated with a registry object by calling <a href="..\wdm\nf-wdm-cmsetcallbackobjectcontext.md">CmSetCallbackObjectContext</a>. This member is defined for Windows Vista and later versions of the Windows operating system.


### -field Reserved

This member is reserved for future use. This member is defined for Windows Vista and later versions of the Windows operating system.


## -remarks
The system passes the <b>REG_QUERY_KEY_SECURITY_INFORMATION</b> structure to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff560903">RegistryCallback</a> routine every time a thread attempts to query a key's security information—for example, when a driver calls <a href="..\ntifs\nf-ntifs-zwquerysecurityobject.md">ZwQuerySecurityObject</a>.

For more information about registry filtering operations, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff545879">Filtering Registry Calls</a>.


## -see-also
<dl>
<dt>
<a href="..\wdm\nf-wdm-cmsetcallbackobjectcontext.md">CmSetCallbackObjectContext</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff560903">RegistryCallback</a>
</dt>
<dt>
<a href="..\ntifs\ns-ntifs-_security_descriptor.md">SECURITY_DESCRIPTOR</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff556635">SECURITY_INFORMATION</a>
</dt>
<dt>
<a href="..\ntifs\nf-ntifs-zwquerysecurityobject.md">ZwQuerySecurityObject</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20REG_QUERY_KEY_SECURITY_INFORMATION structure%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

