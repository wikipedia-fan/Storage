# iSCSI {#firstHeading}

In computing,**iSCSI **is an acronym for**Internet Small Computer Systems Interface**, an [Internet Protocol](https://en.wikipedia.org/wiki/Internet_Protocol)\(IP\)-based storage networking standard for linking data storage facilities. It provides [block-level access](https://en.wikipedia.org/wiki/Block-level_storage) to [storage devices](https://en.wikipedia.org/wiki/Computer_data_storage) by carrying [SCSI](https://en.wikipedia.org/wiki/SCSI) commands over a [TCP/IP](https://en.wikipedia.org/wiki/TCP/IP) network. iSCSI is used to facilitate data transfers over [intranets](https://en.wikipedia.org/wiki/Intranet) and to manage storage over long distances. It can be used to transmit data over [local area networks](https://en.wikipedia.org/wiki/Local_area_network)\(LANs\),[wide area networks](https://en.wikipedia.org/wiki/Wide_area_network)\(WANs\), or the [Internet](https://en.wikipedia.org/wiki/Internet) and can enable location-independent data storage and retrieval.

The [protocol](https://en.wikipedia.org/wiki/Protocol_%28computing%29) allows clients \(calledinitiators\) to send SCSI commands \([CDBs](https://en.wikipedia.org/wiki/SCSI_CDB)\) to storage devices \(targets\) on remote servers. It is a [storage area network](https://en.wikipedia.org/wiki/Storage_area_network) \(SAN\) protocol, allowing organizations to consolidate storage into [storage arrays](https://en.wikipedia.org/wiki/Storage_array) while providing clients \(such as database and web servers\) with the illusion of locally attached SCSI disks.It mainly competes with [Fibre Channel](https://en.wikipedia.org/wiki/Fibre_Channel), but unlike traditional Fibre Channel which usually requires dedicated cabling,iSCSI can be run over long distances using existing network infrastructure.iSCSI was pioneered by IBM and Cisco in 1998 and submitted as a draft standard in March 2000.

# Concepts

In essence, iSCSI allows two hosts to negotiate and then exchange [SCSI](https://en.wikipedia.org/wiki/SCSI) commands using [Internet Protocol](https://en.wikipedia.org/wiki/Internet_Protocol)\(IP\) networks. By doing this, iSCSI takes a popular high-performance local storage bus and emulates it over a wide range of networks, creating a [storage area network](https://en.wikipedia.org/wiki/Storage_area_network)\(SAN\). Unlike some SAN protocols, iSCSI requires no dedicated cabling; it can be run over existing IP infrastructure. As a result, iSCSI is often seen as a low-cost alternative to [Fibre Channel](https://en.wikipedia.org/wiki/Fibre_Channel), which requires dedicated infrastructure except in its [FCoE](https://en.wikipedia.org/wiki/FCoE)\(Fibre Channel over Ethernet\) form. However, the performance of an iSCSI SAN deployment can be severely degraded if not operated on a dedicated network or subnet \(LAN or [VLAN](https://en.wikipedia.org/wiki/VLAN)\), due to competition for a fixed amount of bandwidth.

Although iSCSI can communicate with arbitrary types of SCSI devices, system administrators almost always use it to allow server computers \(such as database servers\) to access disk volumes on storage arrays. iSCSI SANs often have one of two objectives:

### Storage consolidation

Organizations move disparate storage resources from servers around their network to central locations, often in data centers; this allows for more efficiency in the allocation of storage, as the storage itself is no longer tied to a particular server. In a SAN environment, a server can be allocated a new disk volume without any changes to hardware or cabling.

### Disaster recovery

Organizations mirror storage resources from one data center to a remote data center, which can serve as a hot standby in the event of a prolonged outage. In particular, iSCSI SANs allow entire disk arrays to be migrated across a WAN with minimal configuration changes, in effect making storage "routable" in the same manner as network traffic.

### Initiator

Aninitiatorfunctions as an iSCSI client. An initiator typically serves the same purpose to a computer as a SCSI bus adapter would, except that, instead of physically cabling SCSI devices \(like hard drives and tape changers\), an iSCSI initiator sends SCSI commands over an IP network. An initiator falls into two broad types:

A software initiator uses code to implement iSCSI. Typically, this happens in a [kernel-resident](https://en.wikipedia.org/wiki/Kernel_%28computing%29) device driver that uses the existing [network card](https://en.wikipedia.org/wiki/Network_card)\(NIC\) and [network stack](https://en.wikipedia.org/wiki/Network_stack) to emulate SCSI devices for a computer by speaking the iSCSI protocol. Software initiators are available for most popular operating systems and are the most common method of deploying iSCSI.

A hardware initiator uses dedicated hardware, typically in combination with [firmware](https://en.wikipedia.org/wiki/Firmware) running on that hardware, to implement iSCSI. A hardware initiator mitigates the overhead of iSCSI and [TCP](https://en.wikipedia.org/wiki/Transmission_Control_Protocol) processing and [Ethernet interrupts](https://en.wikipedia.org/wiki/Interrupt), and therefore may improve the performance of servers that use iSCSI. An iSCSI [host bus adapter](https://en.wikipedia.org/wiki/Host_bus_adapter)\(more commonly, HBA\) implements a hardware initiator. A typical HBA is packaged as a combination of a Gigabit \(or 10 Gigabit\) Ethernet [network interface controller](https://en.wikipedia.org/wiki/Network_interface_controller), some kind of TCP/IP offload engine \(TOE\) technology and a SCSI bus adapter, which is how it appears to the operating system. An iSCSI HBA can include [PCI](https://en.wikipedia.org/wiki/Conventional_PCI)[option ROM](https://en.wikipedia.org/wiki/Option_ROM) to allow [booting](https://en.wikipedia.org/wiki/Booting) from an iSCSI SAN.

AniSCSI offload engine, oriSOE card, offers an alternative to a full iSCSI HBA. An iSOE "offloads" the iSCSI initiator operations for this particular network interface from the host processor, freeing up CPU cycles for the main host applications. iSCSI HBAs or iSOEs are used when the additional performance enhancement justifies the additional expense of using an HBA for iSCSI,[\[4\]](https://en.wikipedia.org/wiki/ISCSI#cite_note-5)rather than using a software-based iSCSI client \(initiator\). iSOE may be implemented with additional services such as [TCP offload engine](https://en.wikipedia.org/wiki/TCP_offload_engine)\(TOE\) to further reduce host server CPU usage.

### Target

The iSCSI specification refers to a storage resource located on an iSCSI server \(more generally, one of potentially manyinstancesof iSCSI storage nodes running on that server\) as atarget.

An iSCSI target is often a dedicated network-connected hard disk storage device, but may also be a general-purpose computer, since as with initiators, software to provide an iSCSI target is available for most mainstream operating systems.

Common deployment scenarios for an iSCSI target include:

#### Storage array

In a data center or enterprise environment, an iSCSI target often resides in a large storage array. These arrays can be in the form of commodity hardware with [free-software](https://en.wikipedia.org/wiki/Free_software)-based iSCSI implementations, or as commercial products such as in [Quantastor](https://wiki.osnexus.com/index.php?title=What_is_QuantaStor%3F),[CloudByte](https://en.wikipedia.org/wiki/CloudByte),[StorTrends](https://en.wikipedia.org/wiki/StorTrends),[Pure Storage](https://en.wikipedia.org/wiki/Pure_Storage),[HP StorageWorks](https://en.wikipedia.org/wiki/HP_StorageWorks),[EqualLogic](https://en.wikipedia.org/wiki/EqualLogic),[Tegile Systems](https://en.wikipedia.org/wiki/Tegile_Systems),[Nimble storage](https://en.wikipedia.org/wiki/Nimble_storage),[Reduxio](https://en.wikipedia.org/wiki/Reduxio),[IBM Storwize family](https://en.wikipedia.org/wiki/IBM_Storwize_family),[Isilon](https://en.wikipedia.org/wiki/Isilon),[NetApp filer](https://en.wikipedia.org/wiki/NetApp_filer),[EMC Corporation](https://en.wikipedia.org/wiki/EMC_Corporation) NS-series, CX4, VNX, VNXe, VMAX,[Hitachi Data Systems](https://en.wikipedia.org/wiki/Hitachi_Data_Systems) HNAS, or Pivot3 vSTAC.

A storage array usually provides distinct iSCSI targets for numerous clients.

#### Software target

Nearly all modern mainstream server operating systems \(such as [BSD](https://en.wikipedia.org/wiki/BSD),[Linux](https://en.wikipedia.org/wiki/Linux),[Solaris](https://en.wikipedia.org/wiki/Solaris_%28operating_system%29) or [Windows Server](https://en.wikipedia.org/wiki/Windows_Server)\) can provide iSCSI target functionality, either as a built-in feature or with supplemental software. Some specific-purpose operating systems implement iSCSI target support.

#### Logical unit number

In [SCSI](https://en.wikipedia.org/wiki/SCSI) terminology,[LUN](https://en.wikipedia.org/wiki/Logical_unit_number) stands forlogical unit, which are specified by uniquelogical unit numbers. A LUN represents an individually addressable \(logical\) SCSI device that is part of a physical SCSI device \(target\). In an iSCSI environment, LUNs are essentially numbered disk drives.\[[citation needed](https://en.wikipedia.org/wiki/Wikipedia:Citation_needed)\]An initiator negotiates with a target to establish connectivity to a LUN; the result is an iSCSI connection that emulates a connection to a SCSI hard disk. Initiators treat iSCSI LUNs the same way as they would a raw SCSI or IDE hard drive; for instance, rather than mounting remote directories as would be done in [NFS](https://en.wikipedia.org/wiki/Network_File_System_%28protocol%29) or [CIFS](https://en.wikipedia.org/wiki/CIFS) environments, iSCSI systems format and directly manage filesystems on iSCSI LUNs.

In enterprise deployments, LUNs usually represent subsets of large [RAID](https://en.wikipedia.org/wiki/RAID) disk arrays, often allocated one per client. iSCSI imposes no rules or restrictions on multiple computers sharing individual LUNs; it leaves shared access to a single underlying filesystem as a task for the operating system.

### Network booting

For general data storage on an already-booted computer, any type of generic network interface may be used to access iSCSI devices\[[citation needed](https://en.wikipedia.org/wiki/Wikipedia:Citation_needed)\]. However, a generic consumer-grade network interface is not able to boot a diskless computer from a remote iSCSI data source\[[citation needed](https://en.wikipedia.org/wiki/Wikipedia:Citation_needed)\]. Instead, it is commonplace for a server to load its initial operating system from a [TFTP](https://en.wikipedia.org/wiki/TFTP) server or local boot device, and then use iSCSI for data storage once booting from the local device has finished

A separate [DHCP server](https://en.wikipedia.org/wiki/DHCP_server) may be configured to assist interfaces equipped with [network boot](https://en.wikipedia.org/wiki/Network_boot) capability to be able to boot over iSCSI. In this case, the network interface looks for a DHCP server offering a [PXE](https://en.wikipedia.org/wiki/Preboot_Execution_Environment) or [bootp](https://en.wikipedia.org/wiki/Bootp) boot image.This is used to kick off the iSCSI remote boot process, using the booting network interface's [MAC address](https://en.wikipedia.org/wiki/MAC_address) to direct the computer to the correct iSCSI boot target\[[citation needed](https://en.wikipedia.org/wiki/Wikipedia:Citation_needed)\]. One can then use a software-only approach to load a small boot program which can in turn mount a remote iSCSI target as if it was a local SCSI drive and then fire the boot process from said iSCSI target\[[citation needed](https://en.wikipedia.org/wiki/Wikipedia:Citation_needed)\]. This can be achieved using an existing [Preboot Execution Environment](https://en.wikipedia.org/wiki/Preboot_Execution_Environment) \(PXE\) boot ROM, which is available on many wired Ethernet adapters. The boot code can also be loaded from CD/DVD, floppy disk \(or floppy disk image\) and USB storage, or it can replace existing PXE boot code on adapters that can be re-flashed.The most popular free software to offer iSCSI boot support is [iPXE](https://en.wikipedia.org/wiki/IPXE)

Most Intel Ethernet controllers for servers support iSCSI boot.

### Addressing

iSCSI uses TCP \(typically [TCP ports](https://en.wikipedia.org/wiki/TCP_and_UDP_port) 860 and 3260\) for the protocols itself, with higher-level names used to address the objects within the protocol. Special names refer to both iSCSI initiators and targets. iSCSI provides three name-formats:

iSCSI Qualified Name \(IQN\)

Format: The iSCSI Qualified Name is documented in  [RFC 3720](https://tools.ietf.org/html/rfc3720), with further examples of names in [RFC 3721](https://tools.ietf.org/html/rfc3721).Briefly, the fields are:

* literal iqn \(iSCSI Qualified Name\)
* date \(yyyy-mm\) that the naming authority took ownership of the domain
* reversed domain name of the authority \(e.g. org.alpinelinux, com.example, to.yp.cr\)
* Optional ":" prefixing a storage target name specified by the naming authority.

From the RFC:

![](/assets/RFC.png)

Extended Unique Identifier \(EUI\)

Format: eui.{EUI-64 bit address} \(e.g.eui.02004567A425678D\)

T11 Network Address Authority \(NAA\) Format: naa.{NAA 64 or 128 bit identifier} \(e.g.naa.52004567BA64678D\)

IQN format addresses occur most commonly. They are qualified by a date \(yyyy-mm\) because domain names can expire or be acquired by another entity.

The IEEE Registration authority provides EUI in accordance with the EUI-64 standard. NAA is part OUI which is provided by the IEEE Registration Authority. NAA name formats were added to iSCSI in[RFC 3980](https://tools.ietf.org/html/rfc3980), to provide compatibility with naming conventions used in[Fibre Channel](https://en.wikipedia.org/wiki/Fibre_Channel)and[Serial Attached SCSI](https://en.wikipedia.org/wiki/Serial_Attached_SCSI)\(SAS\) storage technologies.

Usually, an iSCSI participant can be defined by three or four fields:

1. Hostname or IP Address \(e.g., "iscsi.example.com"\)
2. Port Number \(e.g., 3260\)
3. iSCSI Name \(e.g., the IQN "iqn.2003-01.com.ibm:00.fcd0ab21.shark128"\)
4. An optional [CHAP](https://en.wikipedia.org/wiki/Challenge-handshake_authentication_protocol) Secret \(e.g., "secretsarefun"\)

### iSNS

iSCSI initiators can locate appropriate storage resources using the [Internet Storage Name Service](https://en.wikipedia.org/wiki/Internet_Storage_Name_Service)\(iSNS\) protocol. In theory, iSNS provides iSCSI SANs with the same management model as dedicated [Fibre Channel](https://en.wikipedia.org/wiki/Fibre_Channel) SANs. In practice, administrators can satisfy many deployment goals for iSCSI without using iSNS.

## Security

### Authentication

iSCSI initiators and targets prove their identity to each other using [CHAP](https://en.wikipedia.org/wiki/Challenge-handshake_authentication_protocol), which includes a mechanism to prevent [cleartext](https://en.wikipedia.org/wiki/Cleartext) passwords from appearing on the wire. By itself, CHAP is vulnerable to [dictionary attacks](https://en.wikipedia.org/wiki/Dictionary_attack),[spoofing](https://en.wikipedia.org/wiki/IP_address_spoofing), and [reflection attacks](https://en.wikipedia.org/wiki/Reflection_attack). If followed carefully, the best practices for using CHAP within iSCSI reduce the surface for these attacks and mitigate the risks.[\[11\]](https://en.wikipedia.org/wiki/ISCSI#cite_note-12)

Additionally, as with all IP-based protocols,[IPsec](https://en.wikipedia.org/wiki/IPsec) can operate at the network layer. The iSCSI negotiation protocol is designed to accommodate other authentication schemes, though interoperability issues limit their deployment. 

### Logical network isolation

To ensure that only valid initiators connect to storage arrays, administrators most commonly run iSCSI only over logically isolated backchannel networks. In this deployment architecture, only the management ports of storage arrays are exposed to the general-purpose internal network, and the iSCSI protocol itself is run over dedicated network segments or [virtual LANs](https://en.wikipedia.org/wiki/Virtual_LAN)\(VLAN\). This mitigates authentication concerns; unauthorized users are not physically provisioned for iSCSI, and thus cannot talk to storage arrays. However, it also creates a [transitive trust](https://en.wikipedia.org/w/index.php?title=Transitive_trust&action=edit&redlink=1) problem, in that a single compromised host with an iSCSI disk can be used to attack storage resources for other hosts.

### Physical network isolation

While iSCSI can be logically isolated from the general network using VLANs only, it is still no different from any other network equipment and may use any cable or port as long as there is a completed signal path between source and target. Just a single cabling mistake by a network technician can compromise the barrier of logical separation, and an accidental bridging may not be immediately detected because it does not cause network errors.

In order to further differentiate iSCSI from the regular network and prevent cabling mistakes when changing connections, administrators may implement self-defined color-coding and labeling standards, such as only using yellow-colored cables for the iSCSI connections and only blue cables for the regular network, and clearly labeling ports and switches used only for iSCSI.

While iSCSI could be implemented as just a VLAN cluster of ports on a large multi-port switch that is also used for general network usage, the administrator may instead choose to use physically separate switches dedicated to iSCSI VLANs only, to further prevent the possibility of an incorrectly connected cable plugged into the wrong port bridging the logical barrier.

### Authorization

Because iSCSI aims to consolidate storage for many servers into a single storage array, iSCSI deployments require strategies to prevent unrelated initiators from accessing storage resources. As a pathological example, a single enterprise storage array could hold data for servers variously regulated by the [Sarbanes–Oxley Act](https://en.wikipedia.org/wiki/Sarbanes%E2%80%93Oxley_Act) for corporate accounting,[HIPAA](https://en.wikipedia.org/wiki/Health_Insurance_Portability_and_Accountability_Act) for health benefits information, and [PCI DSS](https://en.wikipedia.org/wiki/PCI_DSS) for credit card processing. During an audit, storage systems must demonstrate controls to ensure that a server under one regime cannot access the storage assets of a server under another.

Typically, iSCSI storage arrays explicitly map initiators to specific target LUNs; an initiator authenticates not to the storage array, but to the specific storage asset it intends to use. However, because the target LUNs for SCSI commands are expressed both in the iSCSI negotiation protocol and in the underlying SCSI protocol, care must be taken to ensure that access control is provided consistently.

### Confidentiality and integrity

For the most part, iSCSI operates as a cleartext protocol that provides no cryptographic protection for data in motion during SCSI transactions. As a result, an attacker who can listen in on iSCSI Ethernet traffic can:[\[12\]](https://en.wikipedia.org/wiki/ISCSI#cite_note-13)

* Reconstruct and copy the files and filesystems being transferred on the wire
* Alter the contents of files by injecting fake iSCSI frames
* Corrupt filesystems being accessed by initiators, exposing servers to software flaws in poorly tested filesystem code.

These problems do not occur only with iSCSI, but rather apply to any [SAN](https://en.wikipedia.org/wiki/Storage_area_network) protocol without cryptographic security. IP-based security protocols, such as [IPsec](https://en.wikipedia.org/wiki/IPsec), can provide standards-based cryptographic protection to this traffic.

## Implementations

### Operating systems

The dates in the following table denote the first appearance of a native driver in each operating system. Third-party drivers for Windows and Linux were available as early as 2001, specifically for attaching IBM's IP Storage 200i appliance..![](/assets/OS .png)

### Targets

Most iSCSI targets involve disk, though iSCSI tape and medium-changer targets are popular as well. So far, physical devices have not featured native iSCSI interfaces on a component level. Instead, devices with [Parallel SCSI](https://en.wikipedia.org/wiki/Parallel_SCSI) or [Fibre Channel](https://en.wikipedia.org/wiki/Fibre_Channel) interfaces are bridged by using iSCSI target software, external bridges, or controllers internal to the device enclosure.

Alternatively, it is possible to virtualize disk and tape targets. Rather than representing an actual physical device, an emulated virtual device is presented. The underlying implementation can deviate drastically from the presented target as is done with [virtual tape library](https://en.wikipedia.org/wiki/Virtual_tape_library)\(VTL\) products. VTLs use disk storage for storing data written to virtual tapes. As with actual physical devices, virtual targets are presented by using iSCSI target software, external bridges, or controllers internal to the device enclosure.

In the security products industry, some manufacturers use an iSCSI RAID as a target, with the initiator being either an IP-enabled encoder or camera.

### Converters and bridges\[[edit](https://en.wikipedia.org/w/index.php?title=ISCSI&action=edit&section=19)\]

Multiple systems exist that allow Fibre Channel, SCSI and SAS devices to be attached to an IP network for use via iSCSI. They can be used to allow migration from older storage technologies, access to SANs from remote servers and the linking of SANs over IP networks. An iSCSI gateway bridges IP servers to Fibre Channel SANs. The TCP connection is terminated at the gateway, which is implemented on a Fibre Channel switch or as a standalone appliance.



