## Understanding Distributed File System

Administrators have the ability to take shared folders that are located on
different servers and transparently connect them to one or more DFS namespaces.

### Advantages of DFS

+ When a user views this virtual tree, the shared folders appear to be located
  on a single machine
+ __Simplified Data Migration:__ DFS gives you the ability to move data from one
  location to another without the user needing to know the physical location of
  the data.
+ __Security Integration:__ Administrators do not need to configure additional
  security for the DFS shared folders.
+ __Access-Based Enumeration (ABE):__ This feature (disabled by default)
  displays only the files and folders that a user has permissions to access.

### Types of DFS

+ __DFS Replication:__ Manage replication scheduling and bandwidth throttling
  using the DFS management console.
+ __DFS Namespaces:__ The DFS Namespace service is the virtual tree lising in
  the DFS server. An administrator can setup multiple namespaces on the DFS,
  allowing for multiple virtual trees within DFS.