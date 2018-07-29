# _**Logical Unit Number:**_

In computer storage,a logical unit number,or LUN,is a number used to identify\\(识别，标识\\) a logical unit,which is a device addressed by the SCSI protocol or Storage Area Network protocols which encapsulate（封装） SCSI,such as Fibre Channel or iSCSI.

A LUN may be used with any device which supports read/write operations\(操作\),such as a tape drive（磁盘驱动器）,but is most often used refer to a logical disk as created on a SAN.Though not technically correct,the term "LUN" is often also used to refer to th logical disk itself.

# Examples

To provide a practical（实际的） example,a typical（典型的） multidisk drive has multiple（许多的，多样的） physical SCSI ports,each with one SCSI target（目标） address assigned（指派）.An adminstrator may format（格式） the disk array（阵列） as a RAID and then partition（区分，划分） this RAID into several（数个） separate（分离的） storage-volumes（卷）.To represent（代表） each volume,a SCSI target is configured to provide a logical unit.Each SCSI target may provide a multiple volumes,but this does not mean that those volumes are concatenated\(连接的\).The computer that accesses a volume on the disk array identifies which volume to read or write with the LUN of the assciated logical unit .

In another example:a single disk-drive has one physical SCSI port.It usually provides just a single target,which in turn usually just a single logical unit whose LUN is zero.This logical unit represents the entire stroage of the disk drive.

# Use

How to select a LUN:In the early versions of SCSI,an initiator\(创始者\) delivers\(递送\) a Command Descriptor Block\(CDB\) to a target \(physical unit\) and within the CDB is a 3-bit LUN field to identify the logical unit within the target.In current SCSI,the initiator delivers the CDB to a particular\(特定的\) logical unit,so the LUN apprears in the transport layer data structures and not in the CDB.

LUN vs. SCSI Device ID:The LUN is not the only way to identify a logical unit.There is also the  SCSI Device ID ,which identifies a  logical unit uniquely in the world.Labels or serial number stored\(存储\) in a logical unit's storage volume often serve\(提供给\) to identify the logical unit.However,the LUN is the only way for an initiator to address a command to a particular logical unit,so initiators often create,via\(经由\) a discovery process,a mapping\(映射\) table of LUN to other identifiers.

Context sensitive\(上下文\):The LUN identifies a logical unit only within the context of a particular initiator.So two computers that access the same disk volume may konw it by different LUNs.

LUN0:There is one LUN which is required to exist in everytraget:zero.The logical unit with LUN zero is special in that it must implement\(完成\) a few specific\(特殊的，特定的\) commands,most notably\(尤其\) Report LUNs,which is how an initiator can find out all the other LUNs in the target.But LUN zero need not porvide any other services.such as stroage volume.

Many SCSI target contain only one logical unit \(so itsLUN is necessarily zero\).Others have a small number of logical units that correspond to\(相当于\) separate physical devices and have fixed LUNs.A large stroage system have up to thousands of logical units,defined logically,by administrative command,and the administrator may choose the LUN or the system may choose it .

## cXtXdXsX nomenclature\(术语\) in Unix

From the computer perspective\(视角\),SCSI LUN is only a part of the full SCSI address.The full device's address is made from the :

* c-part:controller\(控制器\) ID of the host bus adapter（适配器）

* t-part:target ID identifying the SCSI target on that controller

* d-part: disk ID identifying a LUN on that target

* s-part:slice ID identifying a specific slice on that disk.

In the Unix family of operationg system,these IDs are often combined into a single "name".For example,/dev/dsk/c1t2d3s4 would refer to contrller 1 target 2,disk 3,slice 4.Presently\(现在\) Solaris\(一种网络操作系统\),HP-UX,NCR,and others continue to user "cXtXdXsX" nomenclature,while AIX has abandoned it in favor of\(支持\) more familiar names.HP-UX refers to this sa the Legacy Naming Model since version 11i v3.

## Ohter uses

The term logical unit number also applies to an input/output access channel within certain programming languages.

