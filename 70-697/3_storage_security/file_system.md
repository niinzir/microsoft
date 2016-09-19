__File System Capabilities:__

Feature | FAT32 | NTFS
--- | --- | ---
Suporting OS | All versions above 95 | NT, 2000, XP, 2003, Vista, 7, 8, 10, 2008/R2, 2012/R2
Long filename support | Yes | Yes
Efficient use of disk space | Yes | Yes
Compression support | No | Yes
Encryption Support | No | Yes
Support ofr local security | No | Yes
Support for network security | Yes | Yes
Maximum volume size | 32GB | 16TB with 4KB clusters or 256TB with 64KB clusters

#### FAT32

+ Updated version of FAT
+ Support for smaller cluster sizes
+ Supports drive sizes from 512MB up to 2TB

#### NTFS

+ First introduced with NT
+ Partitions can be up to 16TB with 4KB clusters or 256TB with 64KB clusters

__NTFS Features:__

+ Files can be automatically encrypted and decrypted
+ Reparse points are used with mount points to redirect data as it is written or
  read from a folder to another volume or physical disk.
+ Support for sparse files, which are used by programs that create large files
  but allocate disk space only as needed.
+ Remote storage allows you to extend your disk space by making removale media
  (for example, external tapes) more accessible.
+ Ability to resize volumes and partitions
+ Can use recovery logging on NTFS metadata, which is used for data recovery
  when a power failure or system problem occurs.

### File System Conversion

To convert a partition, you can use the Convert command line utility:

`Convert [drive:]/fs:ntfs`

### Encryption

If files are encrypted using EFS and an administrator has to unencrypt the
files, there are two ways to do this:

+ Log in with the account that encrypted the files
+ Become a recovery agent and manually unecrypt the files manually

### Quotas

Disk quotas give administrators the ability to limit how much storage space a
user can have.

+ __By Volume:__
Set the quota by volume, on a per-volume basis. If you have a hard drive with
C:, D:, and E: volumes, you would have to setup three individual quotas. This
acts as an umbrella over the entire disk.
+ __By User:__
Individually let users have independent quotas that exceed your umbrella quota.
+ __Quota Entries:__
You use quota entries to configure the volume and user quotas
+ __Creating Quota Templates:__
Quota templates are predefined way sto setup quotas. Templates allow you to
setup disk quotas without needing to create a disk quota from scratch. One
advantage of using a template is that when you want to setup disk quotas on
multiple volumes on the same disk, you do not need to re-create the quota on
each volume.

## Configuring Disk Storage

Windows 10 supports three types of disk storage: basic, dynamic, and GUID
Partition Table.

### Basic Storage

Basic storage is backward compatible with otehr OS and can be configured to
support up to four partitions.

Consists of primary and extended partitions and logical drives that exist within
the extended partition.

The first partition that is created on a hard drive is called a primary
partition and is usually represented as the C: drive.

Primary partitions use all of the space that is allocated to the partition, and
a single drive letter is used to represent the partition.

Only a single extended partition is allows on any basic disk.

Each physical drive can have up to four partitions.

You can setup four primary partitions or you can have three primary partitions
and one extended partition.

With an extended partiton, you can allocate the space however you like, and each
subalocation of space (called a logical drive) is represented by a differenct
drive letter.

### Dynamic Storage

Dynamic storage is spported by Windows 2000 and newer and allows storage to be
configured as volumes.

Dynamic storage is Windows 10 feature that consists of a dynamic disk divided
into dynamic volumes.

Cannot contain partitions or logical drives.

Supports three dynamic volume types: simple, spanned, and striped.

Also supports Redundant Array of Independent Disks (RAID).

To setup dynamic storage, you convert or upgrade a basic disk to dynamic disk.

When converting a basic disk to dynamic, you do not lose any of your data. After
the disk is converted, any partititons that existed on the basic disk are
converted to dynamic simple volumes.

#### Simple Volumes

A _simple volume_ contains space from a single dynamic drive.

The space from the single drive can be contiguous or noncontiguous.

Simple volumes are used when you ahve enough disk space on a single drive to
hold your entire volume.

#### Spanned Volumes

A _spanned volume_ consists of disk space on two or more dynamic drives.

Up to 32 dynamic drives can be used ina spanned volume configuration.

When you create spanned volumes, the data is written sequentially, filling space
on one physical drive before writing to space on the next physical drive.

Because data is written sequentially, you do not see any performance
enhancements with spanned volumes as you do with striped.

The main disadvantage of spanned volumes is that if any drive in the spanned
volume set fails, you lose access to all of the data in the spanned set.

#### Striped Volumes

A _striped volume_ stores data in equal stripes between two or more (up to 32)
dynamic drives.

Since the data is written sequentially across the stripe, you can take advantage
of multiple I/O performance and increase the speed as which data reads and
writes take place.

The main disadvantage of striped volumes is that if any drive in the striped
volume set fails, you lose access to all of the data in the striped set.

### Guid Partiton Table (GPT)

GPT support begins with the Windows 2003 SP1 release and allows you to configure
volume sizes larger than 2TB and up to 128 primary partitons.

Basic and dynamic disks use the Master Boot Record (MBR) partition scheme with
Cylinder-Head-Sector (CHS) addresing. CHS allows computers to assign addresses
to data on the computer's hard drives.

GPT uses an addressing scheme called Logical Block Addressing (LBA) which is a
newer method of addressing hard drives.

LBA uses a unique sector number only instead of using the cylinder, head, and
sector number.

Another advantage is that the GPT header and partititon table are written to
both the front and back ends of the disk, which provides for better redundancy.

Benefits over MBR:

+ Volume size larger than 2TB
+ Up to 128 Primary partitions
+ Used for both 32bit and 64 bit Windows 10
+ Includes cyclic redundancy check (CRC) for greater reliability

One disadvantage is you can only convert if the disk is empty or unpartitioned.
