## Quotas

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