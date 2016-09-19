## Storage Spaces

Group hard drives together into a storage pool. Windows 10 users can then use
these storage pool capacities to turn th epools into individual storage spaces.
Storage spaces then show up in File Explorer as regular drives even though they
are virtual drives.

__Simple Spaces:__
+ Work the same as RAID-0 (striped).
+ Increased performance but no data protection.
+ Best used for files that don't need to be protected (temp files, music, etc.)
+ Only require one drive.

__Mirror Spaces:__
+ Work the same as RAID-1 (mirrored).

__Parity Spaces:__
+ Work similar to RAID 5 (stripe with parity).
+ Need minimum three drives for single drive failure and seven drives for two.
