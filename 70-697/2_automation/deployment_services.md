## An overview of Windows Deployment Services

_Windows Deployment Services (WDS)_ is an updated version of Remote Installation
Services (RIS). WDS is a suite of components that allows you to remotely install
Widnows 10 on client comuters. The WDS server must be configured with the
Preboot Execution Environment (PXE) boot files, the images to be deployed to the
client computers, and the answer file. WDS client computers must be PXE-capable.

The WDS clients access the network with the help of a DHCP server. THis allows
the WDS client to remotely install the operation system from the WDS server. The
network environment must be configured with a DHCP server, a DNS server, NTFS
volumes, and Active Directory to connect to the WDS server. No other client
operating system is required to connect to the WDS server. Remote installation
is a good choice for automatic deployment when you need to deploy to large
numbers of computers and the client computers are PXE-compliant

## Advantages of WDS

+ Remotely install Windows oprating systems throughout the network which reduces
  the difficulty and IT manpower cost
+ Deploy multiple imageds for mixed envrionments
+ Use Windows setups including Windows PE, .wim files, and image-based setups.
+ WDS uses mutlicasting to allow for the transmitting data and imaging data to
  communicate to each other.
+ Create reference images using hte Windows Imaging and Configuration Designer
  (Windows ICD) to customize Windows 10 images.
+ Install a driver package to the server and configure the drivers to be
  deployed to client computers at the same time the image is installed.
+ Allows IT departments to standardize Windows 10 installations throughout a
  group or organization.
+ The physical media for Windows 10 does not need to be distributed to all
  comptuers that will be installed.
+ End-user installation deployment can be controlled through the Group Policy
  utility. 

## Disadvantes of WDS

+ WDS can be used only if your network is running Windows SErver 2008, 2008 R2,
  2012, or 2012 R2 with Active Directory installed.
+ The clients that use WDS must be PXE compatible or have a discovery image.

---

WDS can be configured on a Windows Server 2012 or 2012 R2 computer by using the
Windows Deployment Services Configuration Wizard or by using th WDSUTIL
command-line options.
