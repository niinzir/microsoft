## Securing Access to Files and Folders

Access control consists of rights (which pertain to operations on the system)
and permissions (which pertain to operations on specific objects).

The owner of an object or any user who has the necessary rights to modify
permissions can apply permissions to NTFS objects.

If permissions are not explicitly granted within NTFS, then they are implicitly
denied.

Permissions can also be explicitly denied.

Explicit denials override explicitly granted permissions.

### Applying NTFS Permissions

Ultimately, the person who own an object has complete control over the object.

The owner or administrator can configure acceess by allowing or denying NTFS
permissions to users and groups.

Normally, NTFS permissiosn are cumulative, based on group memberships.

Windows 10 offers seven levels of NTFS permissions, plus special permissions:

+ Full Control
+ Modify
+ Read & Execute
+ List Folder Contents
+ Read
+ Write

__Special Permissions:__ This allows you to configure any permissions beyond the
normal permissions, such as auditing, and to take ownership.
