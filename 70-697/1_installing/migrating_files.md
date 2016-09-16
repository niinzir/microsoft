## Migrating Files and Settings

### User State Migration Tool

USMT for Windows 10 is now part of the Windows Assessment and Deployment Kit
(ADK). USMT is similar to Windows Easy Transfer with the following differences:

+ USMT is more configurable and can use XML files to specify which files and
  settings are transferred.

+ USMT is scriptable and uses command-line utilities to asave and restore files
  and settings. USMT consists of two executable files: _Scanstate.exe_ and
  _Loadstate.exe_. In addition, there are three premade migration-rule
  information files: _Migapp.xml_, _Migsys.xml_, and _Miguser.xml_. Finally, you can
  create a _Config.xml_ file that specifies what should and should not be
  migrated. The purpose of these files is as follows:

+ _Scanstate.exe_ collects user data and settings information baased on the
  configuratikon of the _Migapp.xml_, _Migsys.xml_, and _Miguser.xml_ files and
  stores it as an image file. ScanState is used on the machine you are
  migrating from.

+ _Loadstate.exe_ then deposits the information that is collected to a computer
  running a fresh copy of Windows 10. The _Config.xml_ file can be used to help
  exclude files and settings during the LoadState process. The LoadState command
  is used to bring th euser data that was collected from the ScanState utility
  over to the new Windows 10 system.

The following information is migrated:

+ From each user:
  + Documents
  + Video
  + Music
  + Pictures
  + Desktop files
  + Start menu
  + Quick Launch toolbar
  + Internet Explorer Favorites
+ From the All Users profile:
  + Shared documents
  + Shared video
  + Shared music
  + Shared desktop files
  + Shared pictures
  + Shared Start menu
  + Shared Internet Explorer Favorites
  + Files with certain filename extensions, including _.doc, .dot, .rtf, .txt,
    .wps, .wri, .xls, .csv, .wks, .ppt, .pps, .pot, pst,_ and more
  + Access controls lists (ACLs)

USMT will not migrate hardware settings, drivers, passwords, application
binaries, synchronization files, DLL files, or other executables.

A decision point that exists while using USMT is to determine if you want to
perform a side by side installaiton or a wipe-and-laod installation.

__Side by Side Installation:__ A side by side installation means that you have the
new comptuer and the old computer. You use _ScanState_ to collect the user's
data. You then store that data on an intermediate store. After the installation
of Windows 10 on a new machine, you use LoadState to move the data from the
intermediate store to the new computer.

__Wipe and load Installation:__ A wipe and load installation means that you have
the computer only. You will install Windows 10 on the same machine as the
previous operating system. You use ScanState to collect the user's data. You
then store that data on an intermediate store. After the installation of Windows
10 on the machine, you use LoadState to move the data from the intermediate
store to the old computer.

USMT is downloadable software from Microsoft's webstite. In it's simplest form
in the following manner:

1. Run _Scanstate.exe_ on the source computer. _Scanstate.exe_ will copy the
   user state data to an intermediate store. The intermediate store (for
   example a CD) must be large enough to accommodate the data that will be
   transferred. _Scanstate.exe_ would commonly be executed as a shortcut sent
   to users that they would deploy in the evening or through a scheduled script.

2. Install a fresh copy of Windows 10 on the target computer.

3. Run _Loadstate.exe_ on the target computer. _Loadstate.exe_ will access
   the intermediate store to restore the user settings.

When you use USMT, you can create a script that can be run manually or can be
used as an automated process at a scheduled time.

__Options for Scanstate.exe and Loadstate.exe:__

Option | Description
:---: | :---:
/config | Specifies the Config.xml file that should be used
/encrypt | Encrypts the store (_Scanstate.exe_ only)
/decrypt | Decrypts the store (_Loadstate.exe_ only)
/nocompress | Disables data compression
/genconfig | Generates a Config.xml file but does not create a store
/targetxp | Optimizes ScanState for use with Windows XP
/all | Migrates all users
/ue | User exclude: exlucdes a specifies user
/ui | User include: includes the specifies user
/uel | Excludes user based on last login time
/v verboselevel | Used to identify what verbosity level will be associated with the log file on a scale of 0-13, with 0 being the least verbose
