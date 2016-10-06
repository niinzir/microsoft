## Built-in local groups

+ __Administrators__
+ __Backup Operators:__ have permissions to backup and restore the filesystem,
  even if the filesystem is NTFS and they have not been assigned permissions to
  access the filesystem. However, the members of Backup Operators can access the
  filesystem only through the Backup utility. No default members
+ __Cryptographic Operators:__ has access to perform cryptographic operations on
  the computer. No default members
+ __Distributed COM Users:__ has the ability to launch and run Distributed COM
  objects on the computer. No default members
+ __Event Log Readers:__ has access to read the event log on the local computer.
  No default members
+ __Guests:__ has limited access to the computer. By default, the Guest user
  account is a member
+ __IIS_IUSRS:__ used by Internet Information Services (IIS). The NT
  AUTHORITY\IUSR is a member by default
+ __Network Configuration Operators:__ have some administrative rights to manage
  the computer's network configuration
+ __Performance Log Users:__ has the ability to access and schedule logging of
  performance counters and can create and manage trace counters. No default
  members
+ __Performance Monitor Users:__ has the ability to access and view performance
  counter information on the computer. Members can access counters both locally
  and remotely. No default members
+ __Power Users:__ is included in Windows 10 for backward compatability.
  Otherwise, the Power Users group has limited administrative rights. No default
  members
+ __Remote Desktop Users:__ allows members of the group to log on remotely for
  the purpose of using the Remote Desktop service. No default members
+ __Replicator:__ is intended to support directory replication, which is a
  feature used by domain servers. Only domain users who will start the
  replication service should be assigned to this group. No default members
+ __Users:__ intended for end users who should have very limited system access.
  By default, all users who have been created on the computer, except Guest, are
  members of the Users local group
