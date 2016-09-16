## What is Virtualization?

__Server Virtualization:__ This basically enables multiple operating systems to
run on the same physical server. Hyper-V is a server virtualization tool that
allows you to move physical machines to virtual machines and manage them on a
few physical servers. Thus, you will be able to consolidate physical servers.

__Presentation Virtualization:__ When you use _presentation virtualization,_
your applications run on a different computer and only the screen information is
transferred to your computer. An example of presetntation virtualization is
Microsoft Remote Desktop Services in Windows Server 2012 R2.

__Desktop Virtualization:__ _Desktop Virtualization_ provides you with a virtual
machine on your desktop, comparable to server virtualization. You run your
complete operating system and applications in a virtual machine so that your
local physical machine just needs to run a very basic operating system. An
example of this is Microsoft Windows 10 Hyper-V

__Application Virtualization:__ _Application virtualization_ helps prevent
conflicts between applications on the same PC. Thus, it helps you to isolate the
application running environment from the operating system installation
requirements by creating application-specific copies of all shared resources,
and it helps reduce application-to-application incompatibility and testing
needs. An example of an application virtualization tool is Microsoft Application
Virtualization (App-V).

## Manage Virtual Switches

Using Virtual Switch Manager, you can create, manage, and delete virtual
switches. You can define th enetwork type as external, internal only, or
private.

__External:__ Any virtual machine connected to this virtual switch can access
the physical network. You would use this option if you want to allow your
virtual machines to access, for example, other servers on the network or the
Internet. This option is used in production envirionments shere you clients
connect directly to the virtual machines.

__Internal:__ This option allows virtual machines to communicate with each other
as well as the host system but not with the physical network. When you create an
internal network, it also creates a local area connection in Network Connections
that allows the host machine to communcate with the virtual machines. You can
use this if you want to separate your host's network from your virtual networks.

__Private:__ When you use this optiion, virtual machines can communicate with
each other but not with the host system or the physical network; thus, no
network packets are hitting the wire. This option allows virtual machines on the
same Hyper-V host to communicate without using any network traffic.

On the external and internal-only virtual networks, you also can enable virtual
LAN (VLAN) identification.

## Managing Virtual Hard Disks

### Types of Hard Disks

Depending on how you want to use the disk, Hyper-V offers various types:

__Dynamically Expanding:__ This disk starts with a small VHD file and it expands
it on demand. Can be used to clone a local hard drive during creation. This
option is effective when you don't know the exact space needed on the disk and
when you want to preserve hard disk space on the host machine. It is also the
slowest type.

__Fixed Size:__ The size of the VHD file is fixed to the size specified when the
disk is created. This option is faster than a dynamically expanding disk but
slower than a physical disk. This type is ideal for cloning a local hard drive.

__Differencing:__ This type of disk is associated in a parent-child relationship
with anotehr disk. The differencing disk is the child, and the associated
virtual disk is the parent. Differencing disk includ eonly the differences to
the parent disk. By using this ype, you can save a lot of disk space in similar
virtual machines with the same operating systems. Differencing disks are most
commonly found in test environents and should not be used in production
environments.

__Physical (or pass-through disk):__ The virtual machine receives direct
pass-through access to the physical disk for exclusive use. This provides the
highest performance of all disk types and thus should be used for production
servers where performance is the top priority. The drive is not available for
other guest systems. This type is used in high-end data centers and failover
cluster environments.

### Changing Virtual Hard Disks

Hyper-V also provides two tools to manage virtual hard disks:

__Inspect Disk:__ This provieds you with information about the virtual hard
disk. It shows you not only the type of the disk but also information like the
maximum size for dynamically expanding disks and the parent VHD for differencing
disks.

__Edit Disk:__ This provides you with the Edit Virtual Hard Disk Wizard, which
you can use to compact, convert, expand, merge, or reconnect hard disks.
