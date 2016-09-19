### EFS

If files are encrypted using EFS and an administrator has to unencrypt the
files, there are two ways to do this:

+ Log in with the account that encrypted the files
+ Become a recovery agent and manually unecrypt the files manually

## Recovering Encrypted Files

### Using the DRA

DRAs are impleented differently depending on the version of your OS and th
econfiguration of you computer:

+ For Windows 10 that are part of a 2012 R2 Active Directory domain, the domain
  administrator user account is automatically assigned the role of DRA.
+ For Windows 10 that are installed as stand-alone computers or if the computer
  is part of a workgroup, no default DRA is assigned.

You should use extreme caution when using EFS on a stand-alone Windows 10
computer, if the key used to encrypt the files is lost, there is no default
recovery process, and all access to the files will be lost.
