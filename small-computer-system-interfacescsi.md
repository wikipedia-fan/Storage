# **Small Computer System Interface**

## SCSI

Small Computer System Interface** **is a set of standards for physically connecting and transferring data between computers and peripheral devices.   The SCSI standards define commands, protocols, electrical, optical and logica interfaces.SCSI is most commonly used for hard disk drives and [tape drives](https://en.wikipedia.org/wiki/Tape_drive),but it can connect a wide range of other devices, including scanners and CD drives,although not all controllers can handle all devices. The SCSI standard defines command sets for specific peripheral device types;the presence of "unknown" as one of these types means that in theory it can be used as an interface to almost any device, but the standard is highly pragmatic and addressed toward commercial requirements.

The ancestral SCSI standard, X3.131-1986, generally referred to as SCSI-1, was published by the X3T9 technical committee of the American National Standards Institut\(ANSI\)in 1986. SCSI-2 was published in August 1990 as X3.T9.2/86-109, with further revisions in 1994 and subsequent adoption of a multitude of interfaces. Further refinements have resulted in improvements in performance and support for ever-increasing storage data capacity.

## History

### Parallel interface

SCSI is derived from "SASI", the "Shugart AssociatesSystem Interface", developed circa 1978 and publicly disclosed in 1981.Larry Boucher is considered to be the "father" of SASI and ultimately SCSI due to his pioneering work first at Shugart Associates and then at [Adaptec](https://en.wikipedia.org/wiki/Adaptec).

A SASI controller provided a bridge between a hard disk drive's low-level interface and a host computer, which needed to read blocks of data. SASI controller boards were typically the size of a hard disk drive and were usually physically mounted to the drive's chassis. SASI, which was used in mini- and early microcomputers, defined the interface as using a 50-pin flat ribbon connector which was adopted as the SCSI-1 connector. SASI is a fully compliant subset of SCSI-1 so that many, if not all, of the then-existing SASI controllers were SCSI-1 compatible.

Until at least February 1982, ANSI developed the specification as "SASI" and "Shugart Associates System Interface";however, the committee documenting the standard would not allow it to be named after a company. Almost a full day was devoted to agreeing to name the standard "Small Computer System Interface", which Boucher intended to be pronounced "sexy", but ENDL's Dal Allan pronounced the new acronym as "scuzzy" and that stuck.

A number of companies such as NCR Corporation, Adaptec and Optimem were early supporters of SCSI.The NCR facility in Wichita, Kansas is widely thought to have developed the industry's first SCSI controller chip; it worked the first time.

The "small" reference in "small computer system interface" is historical; since the mid-1990s, SCSI has been available on even the largest of computer systems.

Since its standardization in 1986, SCSI has been commonly used in the [Amiga](https://en.wikipedia.org/wiki/Amiga),[Atari](https://en.wikipedia.org/wiki/Atari_Corporation),[Apple Macintosh](https://en.wikipedia.org/wiki/Macintosh) and [Sun Microsystems](https://en.wikipedia.org/wiki/Sun_Microsystems)\(now part of[Oracle Corporation](https://en.wikipedia.org/wiki/Oracle_Corporation)\) computer lines and PC server systems. Apple started using the less-expensive [parallel ATA](https://en.wikipedia.org/wiki/Parallel_ATA)\(PATA, also known asIDE\) for its low-end machines with the [Macintosh Quadra](https://en.wikipedia.org/wiki/Macintosh_Quadra)630 in 1994, and added it to its high-end desktops starting with the Power Macintosh G3 in 1997. Apple dropped on-board SCSI completely in favor of IDE and [FireWire](https://en.wikipedia.org/wiki/IEEE_1394) with the \(Blue & White\) Power Mac G3 in 1999, while still offering a [PCI](https://en.wikipedia.org/wiki/Conventional_PCI) SCSI host adapter as an option on up to the Power Macintosh G4 \(AGP Graphics\) models.[\[9\]](https://en.wikipedia.org/wiki/SCSI#cite_note-9)Sun switched its lower-end range to [Serial ATA](https://en.wikipedia.org/wiki/Serial_ATA)\(SATA\). Commodore included SCSI on the Amiga 3000/3000T systems and it was an add-on to previous Amiga 500/2000 models. Starting with the Amiga 600/1200/4000 systems Commodore switched to the IDE interface. Atari included SCSI as standard in its[Atari MEGA STE](https://en.wikipedia.org/wiki/Atari_MEGA_STE),[Atari TT](https://en.wikipedia.org/wiki/Atari_TT) and [Atari Falcon](https://en.wikipedia.org/wiki/Atari_Falcon)computer models. SCSI has never been popular in the low-priced IBM PC world, owing to the lower cost and adequate performance of ATA hard disk standard. However, SCSI drives and even SCSI [RAIDs](https://en.wikipedia.org/wiki/RAID) became common in PC workstations for video or audio production.

### Modern SCSI

SCSI is available in a variety of interfaces. The first was [parallel SCSI](https://en.wikipedia.org/wiki/Parallel_SCSI) \(also called SCSI Parallel Interface or SPI\), which uses a [parallel](https://en.wikipedia.org/wiki/Parallel_communications)[bus](https://en.wikipedia.org/wiki/Bus_%28computing%29) design. Since 2005, SPI was gradually replaced by [Serial Attached SCSI](https://en.wikipedia.org/wiki/Serial_Attached_SCSI)\(SAS\), which uses a[serial](https://en.wikipedia.org/wiki/Serial_communications) design but retains other aspects of the technology. Many other interfaces which do not rely on complete SCSI standards still implement the [SCSI command protocol](https://en.wikipedia.org/wiki/SCSI#SCSI_command_protocol); others drop physical implementation entirely while retaining the[SCSI architectural model](https://en.wikipedia.org/wiki/SCSI_architectural_model).[iSCSI](https://en.wikipedia.org/wiki/ISCSI), for example, uses [TCP/IP](https://en.wikipedia.org/wiki/TCP/IP) as a transport mechanism, which is most often transported over [Gigabit Ethernet](https://en.wikipedia.org/wiki/Gigabit_Ethernet) or faster [network](https://en.wikipedia.org/wiki/Computer_network) links.

SCSI interfaces have often been included on computers from various manufacturers for use under [Microsoft Windows](https://en.wikipedia.org/wiki/Microsoft_Windows),[classic Mac OS](https://en.wikipedia.org/wiki/Classic_Mac_OS),[Unix](https://en.wikipedia.org/wiki/Unix),[Commodore Amiga](https://en.wikipedia.org/wiki/Commodore_Amiga) and [Linux](https://en.wikipedia.org/wiki/Linux) operating systems, either implemented on the[motherboard](https://en.wikipedia.org/wiki/Motherboard)or by the means of plug-in adaptors. With the advent of [SAS](https://en.wikipedia.org/wiki/Serial_Attached_SCSI) and [SATA](https://en.wikipedia.org/wiki/Serial_ATA) drives, provision for parallel SCSI on motherboards was discontinued.

### Parallel SCSI

Initially, theSCSI Parallel Interface\(SPI\) was the only interface using the SCSI protocol. Its standardization started as a [single-ended](https://en.wikipedia.org/wiki/Single-ended_signaling) 8-bit [bus](https://en.wikipedia.org/wiki/System_bus) in 1986, transferring up to 5 MB/s, and evolved into a low-voltage [differential](https://en.wikipedia.org/wiki/Differential_signaling) 6-bit bus capable of up to 320 MB/s. The last SPI-5 standard from 2003 also defined a 640 MB/s speed which failed to be realized.

Parallel SCSI specifications include several synchronous transfer modes for the parallel cable, and an asynchronous mode. The asynchronous mode is a classic request/acknowledge protocol, which allows systems with a slow bus or simple systems to also use SCSI devices. Faster synchronous modes are used more frequently.

### Other SCSI interfaces![](/assets/import.png)![](/assets/others SCSI interface.png)

## Cabling

### SCSI Parallel Interface

Internal parallel SCSI cables are usually ribbons, with two or more 50–, 68–, or 80–pin connectors attached. External cables are typically shielded \(but may not be\), with 50– or 68–pin connectors at each end, depending upon the specific SCSI bus width supported. The 80–pin Single Connector Attachment\(SCA\) is typically used for hot-pluggable devices.

### Fibre Channel

Fibre Channel can be used to transport SCSI information units, as defined by the Fibre Channel Protocol for SCSI \(FCP\). These connections are hot-pluggable and are usually implemented with optical fiber.

### Serial attached SCSI

Serial attached SCSI \(SAS\) uses a modified Serial ATA data and power cable.

### iSCSI

[iSCSI](https://en.wikipedia.org/wiki/ISCSI)\(Internet Small Computer System Interface\) usually uses [Ethernet](https://en.wikipedia.org/wiki/Ethernet) connectors and cables as its physical transport, but can run over any physical transport capable of transporting [IP](https://en.wikipedia.org/wiki/Internet_Protocol).

### SRP

The [SCSI RDMA Protocol](https://en.wikipedia.org/wiki/SCSI_RDMA_Protocol)\(SRP\) is a protocol that specifies how to transport SCSI commands over a reliable RDMA connection. This protocol can run over any RDMA-capable physical transport, e.g.[InfiniBand](https://en.wikipedia.org/wiki/InfiniBand) or [Ethernet](https://en.wikipedia.org/wiki/Ethernet) when using [RoCE](https://en.wikipedia.org/wiki/RDMA_over_Converged_Ethernet) or [iWARP](https://en.wikipedia.org/wiki/IWARP).

### USB Attached SCSI 

[USB Attached SCSI](https://en.wikipedia.org/wiki/USB_Attached_SCSI) allows SCSI devices to use the [Universal Serial Bus](https://en.wikipedia.org/wiki/Universal_Serial_Bus).

### Automation/Drive Interface

The Automation/Drive Interface − Transport Protocol \(ADT\) is used to connect removable media devices, such as tape drives, with the controllers of the libraries \(automation devices\) in which they are installed. The ADI standard specifies the use of [RS-422](https://en.wikipedia.org/wiki/RS-422) for the physical connections. The second-generation ADT-2 standard defines iADT, use of the ADT protocol over IP \(Internet Protocol\) connections, such as over [Ethernet](https://en.wikipedia.org/wiki/Ethernet). The Automation/Drive Interface − Commands standards \(ADC, ADC-2, and ADC-3\) define SCSI commands for these installations.

## SCSI command protocol

In addition to many different hardware implementations, the SCSI standards also include an extensive set of command definitions. The SCSI command architecture was originally defined for [parallel SCSI](https://en.wikipedia.org/wiki/Parallel_SCSI) buses but has been carried forward with minimal change for use with iSCSI and serial SCSI. Other technologies which use the SCSI command set include the [ATA Packet Interface](https://en.wikipedia.org/wiki/ATAPI),[USB Mass Storage class](https://en.wikipedia.org/wiki/USB_mass_storage_device_class) and [FireWire SBP-2](https://en.wikipedia.org/wiki/Serial_Bus_Protocol_2).

In SCSI terminology, communication takes place between an [initiator](https://en.wikipedia.org/wiki/SCSI_initiator) and a [target](https://en.wikipedia.org/wiki/SCSI_target). The initiator sends a [command](https://en.wikipedia.org/wiki/SCSI_command) to the target, which then responds. SCSI commands are sent in a Command Descriptor Block \([CDB](https://en.wikipedia.org/wiki/SCSI_CDB)\). The CDB consists of a one byte operation code followed by five or more bytes containing command-specific parameters.

At the end of the command sequence, the target returns a [status code](https://en.wikipedia.org/wiki/SCSI_Status_Code) byte, such as 00h for success, 02h for an error \(called a [Check Condition](https://en.wikipedia.org/wiki/SCSI_check_condition)\), or 08h for busy. When the target returns a Check Condition in response to a command, the initiator usually then issues a [SCSI Request Sense command](https://en.wikipedia.org/w/index.php?title=SCSI_Request_Sense_Command&action=edit&redlink=1) in order to obtain a key code qualifier \([KCQ](https://en.wikipedia.org/wiki/KCQ)\) from the target. The Check Condition and Request Sense sequence involves a special SCSI protocol called a [Contingent Allegiance Condition](https://en.wikipedia.org/wiki/SCSI_contingent_allegiance_condition).

There are four categories of SCSI commands: N \(non-data\), W \(writing data from initiator to target\), R \(reading data\), and B \(bidirectional\). There are about 60 different [SCSI commands](https://en.wikipedia.org/wiki/SCSI_command) in total, with the most commonly used being:



