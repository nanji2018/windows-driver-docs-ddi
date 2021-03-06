---
UID: NF:ntifs.FsRtlInitPerStreamContext
title: FsRtlInitPerStreamContext macro
author: windows-driver-content
description: The FsRtlInitPerStreamContext macro initializes a filter driver context structure.
old-location: ifsk\fsrtlinitperstreamcontext.htm
old-project: ifsk
ms.assetid: eea0c2d7-0338-4f34-acae-6ab869011696
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: FsRtlInitPerStreamContext
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: macro
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Desktop
req.target-min-winverclnt: The FsRtlInitPerStreamContext macro is available on Microsoft Windows XP and later, and on the Update Rollup for Windows 2000 Service Pack 4 (SP4).
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: FsRtlInitPerStreamContext
req.alt-loc: ntifs.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: Any level
req.typenames: TOKEN_TYPE
---

# FsRtlInitPerStreamContext macro



## -description
The <b>FsRtlInitPerStreamContext</b> macro initializes a filter driver context structure. 



## -syntax

````
VOID FsRtlInitPerStreamContext(
  _In_ PFSRTL_PER_STREAM_CONTEXT PerStreamContext,
  _In_ PVOID                     OwnerId,
  _In_ PVOID                     InstanceId,
  _In_ PFREE_FUNCTION            FreeCallback
);
````


## -parameters

### -param PerStreamContext [in]

Pointer to a caller-allocated FSRTL_PER_STREAM_CONTEXT structure to be used to maintain context information for a file stream. This structure can be used as is or embedded in a driver-defined per-stream context structure. Both structure types are commonly allocated by calling <a href="..\wdm\nf-wdm-exallocatepoolwithtag.md">ExAllocatePoolWithTag</a>. 


### -param OwnerId [in]

Pointer to a caller-allocated variable that uniquely identifies the owner of the per-stream context structure. The format of this variable is filter driver − specific. Filter writers should choose a value that is both meaningful and convenient, such as the address of a driver object or device object. Callers must specify a non-<b>NULL</b> value for this parameter. 


### -param InstanceId [in]

Pointer to a filter driver − allocated variable that can be used to distinguish among per-stream context structures created by the same filter driver. The format of this variable is filter driver − specific. Filter writers should choose a value that is both meaningful and convenient, such as the address of the stream context object for the file stream. (To get this address from a file object, use the <a href="..\ntifs\nf-ntifs-fsrtlgetperstreamcontextpointer.md">FsRtlGetPerStreamContextPointer</a> macro.) This parameter is optional and can be <b>NULL</b>. 


### -param FreeCallback [in]

Pointer to a callback routine that frees the per-stream context structure. Callers must specify a non-<b>NULL</b> value for this parameter. This routine and its parameters are defined as follows: 

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>typedef
VOID (*PFREE_FUNCTION) (
          IN PVOID Buffer
          );</pre>
</td>
</tr>
</table></span></div>



### -param Buffer

Pointer to the per-stream context structure to be freed. The <i>FreeCallback</i> routine typically casts this pointer to the appropriate structure pointer type and frees it by calling <a href="..\ntddk\nf-ntddk-exfreepool.md">ExFreePool</a>. 

</dd>
</dl>

## -remarks
A file system filter driver uses the <b>FsRtlInitPerStreamContext</b> macro to initialize a newly allocated per-stream context structure before associating it with a file stream. The initialized context structure can be passed as a parameter to <a href="..\ntifs\nf-ntifs-fsrtlinsertperstreamcontext.md">FsRtlInsertPerStreamContext</a>. 

<b>FsRtlInitPerStreamContext</b> stores the address of the <i>FreeCallback</i> routine in the <b>FreeCallback</b> member of the FSRTL_PER_STREAM_CONTEXT structure. 

The <i>FreeCallback</i> routine is called at IRQL &lt;= APC_LEVEL. Usually, it is called at IRQL PASSIVE_LEVEL. 

To associate an initialized per-stream context structure with a file stream, call <a href="..\ntifs\nf-ntifs-fsrtlinsertperstreamcontext.md">FsRtlInsertPerStreamContext</a>. 

After the context structure has been associated with a file stream, it can be retrieved by calling <a href="..\ntifs\nf-ntifs-fsrtllookupperstreamcontext.md">FsRtlLookupPerStreamContext</a> or removed by calling <a href="..\ntifs\nf-ntifs-fsrtlremoveperstreamcontext.md">FsRtlRemovePerStreamContext</a>. 

For more information, see <a href="https://msdn.microsoft.com/d908ee30-a433-460c-8c14-883702b4f810">Tracking Per-Stream Context in a Legacy File System Filter Driver</a>. 


## -see-also
<dl>
<dt>
<a href="..\wdm\nf-wdm-exallocatepoolwithtag.md">ExAllocatePoolWithTag</a>
</dt>
<dt>
<a href="..\ntddk\nf-ntddk-exfreepool.md">ExFreePool</a>
</dt>
<dt>
<a href="..\ntifs\ns-ntifs-_fsrtl_per_stream_context.md">FSRTL_PER_STREAM_CONTEXT</a>
</dt>
<dt>
<a href="..\ntifs\nf-ntifs-fsrtlgetperstreamcontextpointer.md">FsRtlGetPerStreamContextPointer</a>
</dt>
<dt>
<a href="..\ntifs\nf-ntifs-fsrtlinsertperstreamcontext.md">FsRtlInsertPerStreamContext</a>
</dt>
<dt>
<a href="..\ntifs\nf-ntifs-fsrtllookupperstreamcontext.md">FsRtlLookupPerStreamContext</a>
</dt>
<dt>
<a href="..\ntifs\nf-ntifs-fsrtlremoveperstreamcontext.md">FsRtlRemovePerStreamContext</a>
</dt>
<dt>
<a href="..\ntifs\nf-ntifs-fsrtlsetupadvancedheader.md">FsRtlSetupAdvancedHeader</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff547285">FsRtlSupportsPerStreamContexts</a>
</dt>
<dt>
<a href="..\ntifs\nf-ntifs-fsrtlteardownperstreamcontexts.md">FsRtlTeardownPerStreamContexts</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FsRtlInitPerStreamContext function%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

