---
UID: NF:ntifs._FSRTL_ADVANCED_FCB_HEADER.FsRtlNotifyFilterChangeDirectory~r10
title: FsRtlNotifyFilterChangeDirectory function
author: windows-driver-content
description: The FsRtlNotifyFilterChangeDirectory routine creates a notify structure for an IRP_MN_NOTIFY_CHANGE_DIRECTORY request and adds it to the specified notify list.
old-location: ifsk\fsrtlnotifyfilterchangedirectory.htm
old-project: ifsk
ms.assetid: 445b6836-aeac-4183-ba11-a787c1e125ac
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: FsRtlNotifyFilterChangeDirectory
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: This routine is available on Update Rollup for Windows 2000 Service Pack 4 (SP4) and on Windows XP and later.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: FsRtlNotifyFilterChangeDirectory
req.alt-loc: NtosKrnl.exe
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: < APC_LEVEL
req.typenames: TOKEN_TYPE
---

# FsRtlNotifyFilterChangeDirectory function



## -description
The <b>FsRtlNotifyFilterChangeDirectory</b> routine creates a notify structure for an IRP_MN_NOTIFY_CHANGE_DIRECTORY request and adds it to the specified notify list.



## -syntax

````
VOID FsRtlNotifyFilterChangeDirectory(
  _In_     PNOTIFY_SYNC               NotifySync,
  _In_     PLIST_ENTRY                NotifyList,
  _In_     PVOID                      FsContext,
  _In_     PSTRING                    FullDirectoryName,
  _In_     BOOLEAN                    WatchTree,
  _In_     BOOLEAN                    IgnoreBuffer,
  _In_     ULONG                      CompletionFilter,
  _In_opt_ PIRP                       NotifyIrp,
  _In_opt_ PCHECK_FOR_TRAVERSE_ACCESS TraverseCallback,
  _In_opt_ PSECURITY_SUBJECT_CONTEXT  SubjectContext,
  _In_opt_ PFILTER_REPORT_CHANGE      FilterCallback
);
````


## -parameters

### -param NotifySync [in]

Pointer to an opaque synchronization object for the change directory notify list that is pointed to by the <i>NotifyList</i> parameter. 


### -param NotifyList [in]

Pointer to the head of the change directory notify list for the current volume. Each element in the list is an opaque notify structure. 


### -param FsContext [in]

Pointer to a unique value assigned by the file system to identify the notify structure to be created as belonging to a particular file object. If a <i>TraverseCallback</i> routine is supplied, <i>FsContext</i> is passed as the <i>NotifyContext</i> parameter to that routine. 


### -param FullDirectoryName [in]

Pointer to an ANSI or Unicode string that contains the full name for the directory associated with this notify structure. Ignored if <i>NotifyIrp</i> is <b>NULL</b>.


### -param WatchTree [in]

Set to <b>TRUE</b> if all subdirectories of this directory should also be watched. Set to <b>FALSE</b> if only the directory itself is to be watched. Ignored if <i>NotifyIrp</i> is <b>NULL</b>.


### -param IgnoreBuffer [in]

Set to <b>TRUE</b> to ignore any user buffers and force the directory to be reenumerated. This action speeds the operation. Ignored if <i>NotifyIrp</i> is <b>NULL</b>.


### -param CompletionFilter [in]

Bitmask of flags that specify the types of changes to files or directories that should cause the IRPs in the notify list to be completed. The possible flag values are described following.

<table>
<tr>
<th>Flag</th>
<th>Meaning</th>
</tr>
<tr>
<td>
FILE_NOTIFY_CHANGE_FILE_NAME

</td>
<td>
A file has been added, deleted, or renamed in this directory.

</td>
</tr>
<tr>
<td>
FILE_NOTIFY_CHANGE_DIR_NAME

</td>
<td>
A subdirectory has been created, removed, or renamed.

</td>
</tr>
<tr>
<td>
FILE_NOTIFY_CHANGE_NAME

</td>
<td>
This directory's name has changed.

</td>
</tr>
<tr>
<td>
FILE_NOTIFY_CHANGE_ATTRIBUTES

</td>
<td>
The value of an attribute of this file, such as last access time, has changed.

</td>
</tr>
<tr>
<td>
FILE_NOTIFY_CHANGE_SIZE

</td>
<td>
This file's size has changed.

</td>
</tr>
<tr>
<td>
FILE_NOTIFY_CHANGE_LAST_WRITE

</td>
<td>
This file's last modification time has changed.

</td>
</tr>
<tr>
<td>
FILE_NOTIFY_CHANGE_LAST_ACCESS

</td>
<td>
This file's last access time has changed.

</td>
</tr>
<tr>
<td>
FILE_NOTIFY_CHANGE_CREATION

</td>
<td>
This file's creation time has changed.

</td>
</tr>
<tr>
<td>
FILE_NOTIFY_CHANGE_EA

</td>
<td>
This file's extended attributes have been modified.

</td>
</tr>
<tr>
<td>
FILE_NOTIFY_CHANGE_SECURITY

</td>
<td>
This file's security information has changed.

</td>
</tr>
<tr>
<td>
FILE_NOTIFY_CHANGE_STREAM_NAME

</td>
<td>
A file stream has been added, deleted, or renamed in this directory.

</td>
</tr>
<tr>
<td>
FILE_NOTIFY_CHANGE_STREAM_SIZE

</td>
<td>
This file stream's size has changed.

</td>
</tr>
<tr>
<td>
FILE_NOTIFY_CHANGE_STREAM_WRITE

</td>
<td>
This file stream's data has changed.

</td>
</tr>
</table>
 

<i>CompletionFilter</i> is ignored if <i>NotifyIrp</i> is <b>NULL</b>.


### -param NotifyIrp [in, optional]

Pointer to the IRP to be added to the notify list. If <i>NotifyIrp</i> is <b>NULL</b>, this means that the file stream represented by the file object (identified by the <i>FsContext</i> parameter) is being deleted.


### -param TraverseCallback [in, optional]

Optional pointer to a callback routine to be invoked when a change occurs in a subdirectory being watched in a directory tree. This lets the file system check whether the watcher has traverse access to that directory. Such a caller-supplied routine is declared as follows:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>NTSTATUS
(*PCHECK_FOR_TRAVERSE_ACCESS) (
    IN PVOID NotifyContext,                     // FsContext
    IN PVOID TargetContext,                     // Context pointer
    IN PSECURITY_SUBJECT_CONTEXT SubjectContext // SubjectContext
    );</pre>
</td>
</tr>
</table></span></div>
For more information about the <i>TargetContext</i> parameter, see the <i>TargetContext</i> parameter of <a href="..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlnotifyfullreportchange~r8.md">FsRtlNotifyFullReportChange</a>. <i>TraverseCallback</i> is ignored if <i>NotifyIrp</i> is <b>NULL</b>.


### -param SubjectContext [in, optional]

Pointer to a context structure to be passed to <i>TraverseCallback</i>. <b>FsRtlNotifyFilterChangeDirectory</b> releases the context and frees the structure after using it. Ignored if <i>NotifyIrp</i> is <b>NULL</b>. If a <i>TraverseCallback</i> routine is supplied, <i>SubjectContext</i> is passed as the <i>SubjectContext</i> parameter to that routine.


### -param FilterCallback [in, optional]

Optional pointer to a callback routine to be invoked when a change occurs to the directory. If this callback routine returns <b>TRUE</b>, <a href="..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlnotifyfilterreportchange~r9.md">FsRtlNotifyFilterReportChange</a> completes the pending IRP_MN_NOTIFY_CHANGE_DIRECTORY requests in the notify list; otherwise, it does not. Such a caller-supplied routine is declared as follows: 

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>BOOLEAN
(*PFILTER_REPORT_CHANGE) (
    IN PVOID NotifyContext,                     // FsContext
    IN PVOID FilterContext                      // Context pointer
    );</pre>
</td>
</tr>
</table></span></div>

## -returns
None


## -remarks
<b>FsRtlNotifyFilterChangeDirectory</b> is called by a file system that has received an IRP with major function code <a href="https://msdn.microsoft.com/library/windows/hardware/ff548658">IRP_MJ_DIRECTORY_CONTROL</a>, minor function code IRP_MN_NOTIFY_CHANGE_DIRECTORY. 

The file system calls <b>FsRtlNotifyFilterChangeDirectory</b> to create a notify structure to hold the IRP and add the notify structure to the notify list for the current volume. 

If <i>NotifyIrp</i> is <b>NULL</b>, <b>FsRtlNotifyFilterChangeDirectory</b> checks whether the notify list already contains any pending IRPs whose file objects match the given <i>FsContext</i> value and, if so, completes the IRPs with STATUS_DELETE_PENDING. 

If <i>NotifyIrp</i> is not <b>NULL</b>, <b>FsRtlNotifyFilterChangeDirectory</b> does the following:

Checks whether the IRP's file object has undergone cleanup. If so, <b>FsRtlNotifyFilterChangeDirectory</b> completes the IRP with status STATUS_NOTIFY_CLEANUP and does not add it to the notify list. 

If the IRP's file object has not undergone cleanup, <b>FsRtlNotifyFilterChangeDirectory</b> checks whether the notify list already contains a notify structure for the given <i>FsContext</i> value. If such a notify structure is found, and there are pending changes to report, <b>FsRtlNotifyFilterChangeDirectory</b> completes <i>NotifyIrp</i>. If a notify structure is found, but there are no pending changes to report, <b>FsRtlNotifyFilterChangeDirectory</b> marks the IRP pointed to by <i>NotifyIrp</i>  as pending and inserts it into the list of notify IRPs in the notify structure. If no such notify structure is found, <b>FsRtlNotifyFilterChangeDirectory</b> marks the IRP pointed to by <i>NotifyIrp</i>  as pending, creates a notify structure, and inserts it into the notify list. 

When a change occurs to the directory, the file system calls <a href="..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlnotifyfilterreportchange~r9.md">FsRtlNotifyFilterReportChange</a> to complete the pending IRP_MN_NOTIFY_CHANGE_DIRECTORY requests in the notify list. 


## -see-also
<dl>
<dt>
<a href="..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlnotifyfilterreportchange~r9.md">FsRtlNotifyFilterReportChange</a>
</dt>
<dt>
<a href="..\rxprocs\nf-rxprocs-fsrtlnotifyfullchangedirectory.md">FsRtlNotifyFullChangeDirectory</a>
</dt>
<dt>
<a href="..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlnotifyfullreportchange~r8.md">FsRtlNotifyFullReportChange</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff548658">IRP_MJ_DIRECTORY_CONTROL</a>
</dt>
<dt>
<a href="..\wdm\ns-wdm-_security_subject_context.md">SECURITY_SUBJECT_CONTEXT</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FsRtlNotifyFilterChangeDirectory routine%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

