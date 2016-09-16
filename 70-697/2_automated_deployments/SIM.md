## Using Windows System Image Manager to Create Answer Files

There are several advantages to using Windows SIM to create answer files:

+ You can easily create and edit answer files through a graphical interface,
  which reduces syntax errors.
+ It simplifies the addition of user-specific or computer-specific configuration
  information.
+ You can validate exisisting answer files against newly created images.
+ You can include additional application and device drivers in the anser file.

## Configuring Components through Windows System Image Manager

The following list defines which components can be configured through Windows
SIM:

+ __auditSystem:__ Adds additional device drivers, specifies firewall settings,
  and applies a name to the system when the image is booted into audit mode.
  Audit mode is initiated by using the `sysprep /audit` command.

+ __auditUser:__ Executes `RunSynchronous` or `RunAsynchronous` commands when
  the image is booted into audi mode. Audit mode is initiated by using the
  `sysprep /audit` command.

+ __generalize:__ Removes system-specific information from an image so that the
  image can be used as a reference image. The settings specifies in the
  generalize component will be applied only if the `sysprep /generalize` command
  is used.

+ __offlineServicing:__ Specifies the language packs and packages to appl yto an
  image prior to the image being extracted to the hard disk.

+ __oobeSystem:__ Specifies the settings to apply to the computer the first time
  the computer is booted into the Windows Welcome screen, which is also known as
  the Out-Of-Box Experience (OOBE). To boot to the WElcome screen, the `sysprep
  /oobe` command should be used.
 
+ __specialize:__ Configures the specific settings for the target computer, such
  as network settings and domain information. This configuration pass is used in
  conjunciton with the generalzie configuration pass.

+ __Windows PE:__ Sets the Windows PE-specfiic configuration settings as well as
  several Windows Setup settings, such as partitioning and formatting the hard
  disk, selecting an image, and applying a product key.
