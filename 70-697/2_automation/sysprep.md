## An Overview of the System Preparation Tool and Disk Imaging

The _System Preparation Tool,_ or _Sysprep_ (Sysprep.exe), is used to prepare a
computer for disk imaging, and the disk image can then be captured using Image
Capture Wizard (an imaging-management tool included with Windows 10) or
thrid-party imaging software.

To perform an unattended installation, Sysprep prepares the reference computer
by stripping away any computer-specific data, such as the security identifier
(SID), which is used to uniquely identify each computer on the network; any
event logs; an dnay other unique system information. Sysprep also detects any
Plug and Play devices that are installed and can adjust dynamically for any
computers that have different hardware installed. 

The out-of-the-box experience makes the newly built system work as if you took
the new syste mright out of the manufacturer's box.

Sysprep is a utility that is good only for setting up a new machine. You do not
use Sysprep to image a computer for upgrading a current machine. There are a few
switches that you can use in cunjunction with Sysprep to configure the Sysprep
utility for you rspecific needs

__Sysprep Switches__

Switch | Explanation
--- | ---
/pnp | Forces a mino-setup wizard to start at reboot so that all Plug and Play devices can be recognized
/generalize | This allows Sysprep to remove all system-specific data from the Sysprep image
/oobe | Initiates the Windows Welcome screen at the next reboot
/audit | Initiates Sysprep in audit mode
/nosidgen | Sysprpe does not generate a new SID on the computer restart. Froces a mini-setup on restart
/reboot | Stops and restarts the computer system
/quiet | Runs without any confirmation dialog messages being displayed
/mini | Tells Sysprep to run the mini-setup on the next reboot

Sysprep rules:

+ The Windows activation clock starts to decrease as soon as Windows starts for
  the first time. You can restart the Windows activation clock only three times
  using Sysprep.
+ The computer on which you're running Sysprep has to be a member of a
  work-group. The machine can't be part of a domain. If the computer is a member
  of the domain, when you run Sysprep, the computer will automatically be
  removed from the domain.
+ When installing the image, the system will prompt you for a product key.
  During install you can use an answer file, which in turn will have all the
  information needed for the install, and you will not be prompted for any
  information.
+ A third party utility or Image Capture Wizard is required to deploy the image
  that is create from Sysprep.
+ If you are using Sysprpe to capture an NTFS partition, any files or folders
  that are encrypted will become corrupt and unreadable.

Running Sysprep on a machine:

1. Install the Windows 10 operating system
2. Install all components
3. Run `sysprep /generalize` to create the image

When you image a computer using Sysprep, a Windows image (.wim) file is create.
Most third party imaging software products can work with the Windows image file.

## Advantages of Sysprep

+ For large numbers of computers with similar hardware, it greatly reduces
  deployment time by copying the OS, applications, and desktop settings from a
  reference computer to an iamge, which can then be deplyed to multiple
  computers.
+ Using disk imaging facilitates the standardization of desktops, administrative
  policies, and restriction throughout an organization.
+ Reference images can be copied across a network connection or through DVDs
  that are physically distributed to client computers.

## Disadvantages of Sysprep

+ Image Capture Wizard, third party iaging software, or hardware
  disk-duplication devices must be used for an image-based setup.
+ The version of Sysprep that shipped with Windows 10 must be used. An older
  version of Sysprep cannot be used on a Windows 10 image.
+ Sysprep will not detect any hardware that is not Plug and Play compliant

## Preparing a Windows 10 Installation

1. Install Windows 10 on the source computer. The computer should have a similar
   hardware configuration to that of th edestination comptuer. The source
   computer should not be a member of a domain

2. Log on to th esource computer as administrator and, if desired, install and
   configure any applications, files (such as newer versions of Plug and Play
   drivers), or custom settings (for example, a custom desktop) that will be
   applied to the target computer.

3. Verify that your image meets the specified configuration criteria and that
   all applications are properly installed and working.

4. Open Windows Exploerer and navigate to `C:\$WINDIR%\System32\sysprep`. Double
   click the Sysprep application icon.

5. The Windows System Preparation Tool dialog box appears. Select the
   appropriate options for your configuration.

6. If configured to do so, Windows 10 will be rebooted into setup mdoe, and you
   will be prompted to enter the appropriate setup informatin.

7. You will now be able to use imaging software to create an image fo the
   computer to deploy to other computers
