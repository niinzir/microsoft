## RAID Levels

Windows 10 allows for configuration of three main levels:

__RAID-0 (Striped):__
+ No data recoverability, but better performance
+ Minimum of two hard disks, work together as a single volume.
+ If yo ulose either disk, you lose the entire striped volume.

__RAID-1 (Mirrored):__
+ Setup two volumes or disks that mirror each other.
+ If you lose one disk or volume, you can boot to the second disk or volume.

__RAID-5:__
+ Previously known as a stripe set with parity.
+ Minimum of 3 disks that work together as one volume.
+ The volume uses a parity bit, which allows you to recover your data in the
  event of a single hard disk failure.