# _**Logical Unit Number:**_

In computer storage,a logical unit number,or LUN,is a number used to identify\\(识别，标识\\) a logical unit,which is a device addressed by the SCSI protocol or Storage Area Network protocols which encapsulate（封装） SCSI,such as Fibre Channel or iSCSI.

A LUN may be used with any device which supports read/write operations,such as a tape drive,but is most often used refer to a logical disk as created on a SAN.Though not technically correct,the term "LUN" is often also used to refer to th logical disk itself.

# Examples

To provide a practical example,a typical multidisk drive has multipe physical SCSI ports,each with one SCSI target address assigned.An adminstrator may format the disk array as a RAID and then partition this RAID into several separate storage-volumes.To represent each volume,a SCSI target is configured to provide a logical unit.Each SCSI target may provide a multiple volumes,but this does not mean that those volumes,but this does not mean that those volumes are concatenated.The computer that accesses a volume on the disk array identifies which volume to read or write with the LUN of the assciated logical unit .

In another example:a single disk-drive has one physical SCSI port.It usually provides just a single target,which in turn usuall just a single logical unit whose LUN is zero.This logical unit represents the entire stroage of the disk drive.

# Use

How to select a LUN:In the early versions of SCSI,an initiator delivers a Command Descriptor Block\\(CDB\\) to a target \\(physical unit\\) and within the CDB is a 3-bit LUN field to identify the logical unit within the target.In current SCSI,the initiator delivers the CDB to a particular logical unit,so the LUN apprears in the transport layer data structures and not in the CDB.

LUN vs. SCSI Device ID:The LUN is not the only way to identify a logical unit.There is also the  SCSI Device ID ,which identifies a  logical unit uniquely in the world.Labels or serial number stored in a logical unit's storage volume often serve to identify the logical unit.However,the LUN is the only way for an initiator to address a command to a particular logical unit,so initiators 

