---
Description: A writers participation in incremental and differential backups typically takes place while handling Identify (CVssWriterOnIdentify), PrepareForBackup (CVssWriterOnPrepareBackup), and PostSnapshot (CVssWriterOnPostSnapshot) events.
ms.assetid: 85c4e003-b531-4283-83aa-dd5cc53f35b1
title: Writer Role in VSS Incremental and Differential Backups
ms.date: 05/31/2018
ms.topic: article
ms.author: windowssdkdev
ms.prod: windows
ms.technology: desktop
---

# Writer Role in VSS Incremental and Differential Backups

A writer's participation in incremental and differential backups typically takes place while handling [*Identify*](vssgloss-i.md#base-vssgloss-identify-event) ([**CVssWriter::OnIdentify**](/windows/win32/VsWriter/nf-vswriter-cvsswriter-onidentify?branch=master)), [*PrepareForBackup*](vssgloss-p.md#-win32-vssgloss-prepareforbackup-event) ([**CVssWriter:OnPrepareBackup**](/windows/win32/VsWriter/nf-vswriter-cvsswriter-onpreparebackup?branch=master)), and *PostSnapshot* ([**CVssWriter:OnPostSnapshot**](/windows/win32/VsWriter/nf-vswriter-cvsswriter-onpostsnapshot?branch=master)) events. How a writer participates is shaped by whether it supports backup stamps and last modification times, and whether the requester running the backup supports [*partial file operations*](vssgloss-p.md#base-vssgloss-partial-file-support).

## Handling Identify Events during Incremental and Differential Backups

While handling the Identify event, writers establish their basic architecture for incremental and differential backup operation through the backup schema ([**VSS\_BACKUP\_SCHEMA**](/windows/win32/Vss/ne-vss-_vss_backup_schema?branch=master)) and file specification backup type ([**VSS\_FILE\_SPEC\_BACKUP\_TYPE**](/windows/win32/Vss/ne-vss-_vss_file_spec_backup_type?branch=master)) masks.

A writer indicates which operations it supports in its Writer Metadata Document by creating a bit mask of [**VSS\_BACKUP\_SCHEMA**](/windows/win32/Vss/ne-vss-_vss_backup_schema?branch=master) values and passing it to the [**IVssCreateWriterMetadata::SetBackupSchema**](/windows/win32/VsWriter/nf-vswriter-ivsscreatewritermetadata-setbackupschema?branch=master) method. With this, a writer can indicate whether it supports the following:

-   Incremental backups (**VSS\_BS\_INCREMENTAL**)
-   Differential backups (**VSS\_BS\_DIFFERENTIAL**)
-   Incremental and differential backups cannot be mixed (**VSS\_BS\_EXCLUSIVE\_INCREMENTAL\_DIFFERENTIAL**)
-   Incremental and differential backups using backup stamps (**VSS\_BS\_TIMESTAMPED**)
-   Incremental and differential backups on the basis of information about a file's last modification (**VSS\_BS\_LAST\_MODIFY**)

Writers use the file specification backup type mask to provide file set level information to requesters on how to include files in an incremental or differential backup.

A writer can set a file set's file specification backup type mask when it adds the file set to a component by creating a bit mask of [**VSS\_FILE\_SPEC\_BACKUP\_TYPE**](/windows/win32/Vss/ne-vss-_vss_file_spec_backup_type?branch=master) values and passing it to [**IVssCreateWriterMetadata::AddDatabaseFiles**](/windows/win32/VsWriter/nf-vswriter-ivsscreatewritermetadata-adddatabasefiles?branch=master), [**IVssCreateWriterMetadata::AddDatabaseLogFiles**](/windows/win32/VsWriter/nf-vswriter-ivsscreatewritermetadata-adddatabaselogfiles?branch=master), or [**IVssCreateWriterMetadata::AddFilesToFileGroup**](/windows/win32/VsWriter/nf-vswriter-ivsscreatewritermetadata-addfilestofilegroup?branch=master).

There are three "backup required" values of the [**VSS\_FILE\_SPEC\_BACKUP\_TYPE**](/windows/win32/Vss/ne-vss-_vss_file_spec_backup_type?branch=master) enumeration that affect differential and incremental backups:

-   **VSS\_FSBT\_ALL\_BACKUP\_REQUIRED**
-   **VSS\_FSBT\_INCREMENTAL\_BACKUP\_REQUIRED**
-   **VSS\_FSBT\_DIFFERENTIAL\_BACKUP\_REQUIRED**

There are three "shadow copy required" values:

-   **VSS\_FSBT\_ALL\_SNAPSHOT\_REQUIRED**
-   **VSS\_FSBT\_INCREMENTAL\_SNAPSHOT\_REQUIRED**
-   **VSS\_FSBT\_DIFFERENTIAL\_SNAPSHOT\_REQUIRED**

File sets tagged with a file specification backup type of "shadow copy required" indicate whether a requester needs to copy data from a shadow copy when performing INCREMENTAL, DIFFERENTIAL, or ALL (which includes both incremental and differential operations) backup operations.

The "backup required" flag, applied to INCREMENTAL, DIFFERENTIAL, or ALL backup operations, indicates that the writer expects a copy of the current version of the file set to be available following the restore of any backup operation. Typically, this means that if a file set is tagged with "backup required," all its members will be copied to backup media during an incremental or differential backup, regardless of when their backup or modification last occurred.

By default, file sets are added to components with a file specification backup type of **VSS\_FSBT\_ALL\_BACKUP\_REQUIRED** \| **VSS\_FSBT\_ALL\_SNAPSHOT\_REQUIRED**. Therefore, unless a writer developer decides not to use the default (by choosing another file specification backup type, using partial file operations, or using differenced files), the files in most file sets will typically be copied in their entirety to backup media.

At this point, the writer's Writer Metadata Document is fully populated with most of information a requester will need to start a differential or incremental backup. Addition specification of file set or file level information to support the backup will be handled during the [**PrepareForBackup**](/windows/win32/VsBackup/nf-vsbackup-ivssbackupcomponents-prepareforbackup?branch=master) event.

## Handling PrepareForBackup Events during Incremental and Differential Backups

Before the requester proceeds with the actual backup operation, writers can modify the specification of an [*incremental*](vssgloss-i.md#base-vssgloss-incremental-backup-operations) or [*differential*](vssgloss-d.md#base-vssgloss-differential-backup-operations) backup by altering the requester's Backup Components Document through the [**IVssComponent**](/windows/win32/VsWriter/nl-vswriter-ivsscomponent?branch=master) interface.

Because the writers use the [**IVssComponent**](/windows/win32/VsWriter/nl-vswriter-ivsscomponent?branch=master) interface, they typically perform these preparations while handling the [**PrepareForBackup**](/windows/win32/VsBackup/nf-vsbackup-ivssbackupcomponents-prepareforbackup?branch=master) event.

In [**CVssWriter:OnPrepareBackup**](/windows/win32/VsWriter/nf-vswriter-cvsswriter-onpreparebackup?branch=master), writers can more precisely specify how some files are to be evaluated for backup, specify what mechanisms should be used in backing them up, and possibly set backup stamps.

<dl> <dt>

<span id="Partial_Files"></span><span id="partial_files"></span><span id="PARTIAL_FILES"></span>Partial Files
</dt> <dd>

If a requester supports them, a writer can choose to have an incremental or differential backup implemented by using partial file operations. (Writers can determine if a requester supports partial file operations by calling [**CVssWriter::IsPartialFileSupportEnabled**](/windows/win32/VsWriter/nf-vswriter-cvsswriter-ispartialfilesupportenabled?branch=master).)

Writers use [**IVssComponent::AddPartialFile**](/windows/win32/VsWriter/nf-vswriter-ivsscomponent-addpartialfile?branch=master) to indicate those portions of the selected files to be backed up during the incremental or differential operation. Requesters must respect this specification, and must always back up the specified sections of the files. (See [Working with Partial Files](working-with-partial-files.md) for more information on partial file operations.)

Using [**IVssComponent::AddPartialFile**](/windows/win32/VsWriter/nf-vswriter-ivsscomponent-addpartialfile?branch=master), a writer can add a file to the backup that was not previously added to one of its component sets (by [**IVssCreateWriterMetadata::AddDatabaseFiles**](/windows/win32/VsWriter/nf-vswriter-ivsscreatewritermetadata-adddatabasefiles?branch=master), [**IVssCreateWriterMetadata::AddDatabaseLogFiles**](/windows/win32/VsWriter/nf-vswriter-ivsscreatewritermetadata-adddatabaselogfiles?branch=master), or [**IVssCreateWriterMetadata::AddFilesToFileGroup**](/windows/win32/VsWriter/nf-vswriter-ivsscreatewritermetadata-addfilestofilegroup?branch=master)) as a partial file. Any new files added to the backup in this manner must be on a volume that already is being shadow copied for this backup.

If a file is involved with partial file operations, this supersedes any file specification backup type, which is ignored.

</dd> <dt>

<span id="Differenced_Files"></span><span id="differenced_files"></span><span id="DIFFERENCED_FILES"></span>Differenced Files
</dt> <dd>

Writers that support a last modified backup schema (**VSS\_BS\_SCHEMA**) can add [*differenced files*](vssgloss-d.md#base-vssgloss-differenced-files) to an incremental or differential backup.

In specifying a differenced file, a writer uses [**IVssComponent::AddDifferencedFileByLastModifyTime**](/windows/win32/VsWriter/nf-vswriter-ivsscomponent-adddifferencedfilesbylastmodifytime?branch=master) and specifies a path, a file name, and a recursive flag—however, these do not have to match a file set included in any component.

In fact, a writer can add a file not previously added to one of its component sets (by [**IVssCreateWriterMetadata::AddDatabaseFiles**](/windows/win32/VsWriter/nf-vswriter-ivsscreatewritermetadata-adddatabasefiles?branch=master), [**IVssCreateWriterMetadata::AddDatabaseLogFiles**](/windows/win32/VsWriter/nf-vswriter-ivsscreatewritermetadata-adddatabaselogfiles?branch=master), or [**IVssCreateWriterMetadata::AddFilesToFileGroup**](/windows/win32/VsWriter/nf-vswriter-ivsscreatewritermetadata-addfilestofilegroup?branch=master)) to the backup as a differenced file. Any new files added to the backup in this manner must be on a volume that already is being shadow copied for this backup.

Typically, a writer will also specify a time of last modification when adding a differenced file—based on the writer's own history mechanism. This last modification time, if specified, must always be used by requesters in determining if a file needs to be included in an incremental or differential backup.

A writer may choose not to specify a last modification time when adding a differenced file to an incremental or differential backup set. If this is the case, requesters are free to use their own mechanisms—for instance, logs of previous backups or file system information—to determine whether the differenced file should be included in an incremental or differential backup.

The file specification backup type of any differenced file is ignored.

</dd> <dt>

<span id="Backup_Stamps"></span><span id="backup_stamps"></span><span id="BACKUP_STAMPS"></span>Backup Stamps
</dt> <dd>

Writers that support backup stamps (**VSS\_BS\_TIMESTAMP**) have their own private format for storing information about when a backup last occurred. This information is generated by the writer during backup.

The backup stamp is stored in the Backup Components Document as a string by the [**IVssComponent::SetBackupStamp**](/windows/win32/VsWriter/nf-vswriter-ivsscomponent-setbackupstamp?branch=master) method. The backup stamp applies to all file sets in the component (or component set) corresponding to the instance of the [**IVssComponent**](/windows/win32/VsWriter/nl-vswriter-ivsscomponent?branch=master).

If a requester has access to the backup stamp of a previous backup, it will have made it available to the writer by calling [**IVssBackupComponents::SetPreviousBackupStamp**](/windows/win32/VsBackup/nf-vsbackup-ivssbackupcomponents-setpreviousbackupstamp?branch=master).

A writer then can examine this time stamp using [**IVssComponent::GetPreviousBackupStamp**](/windows/win32/VsWriter/nf-vswriter-ivsscomponent-getpreviousbackupstamp?branch=master).

Note that the requester merely stores and returns the string containing the backup stamp. It does not know anything about the string's format or how to use it; only the writer has that information.

A writer may choose to update the current backup stamp using [**IVssComponent::SetBackupStamp**](/windows/win32/VsWriter/nf-vswriter-ivsscomponent-setbackupstamp?branch=master) after it has called [**IVssComponent::GetPreviousBackupStamp**](/windows/win32/VsWriter/nf-vswriter-ivsscomponent-getpreviousbackupstamp?branch=master), thus recording in its own format the date of the current incremental or differential backup operation.

</dd> </dl>

 

 


