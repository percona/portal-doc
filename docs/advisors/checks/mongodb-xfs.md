# MongoDB XFS Filesystem type

## Description
This check returns a warning if DBPATH is not using the XFS filesystem type.

## Resolution

As per [MongoDB Documentation](https://www.mongodb.com/docs/v6.0/administration/production-notes/#std-label-prod-notes-linux-file-system), when using a WiredTiger storage engine, use of the XFS file system type is strongly recommended for data bearing nodes to avoid performance issues that may occur when using EXT4 with the WiredTiger engine.

- In general, if you use the XFS file system, use at least version 2.6.25 of the Linux Kernel.
- If you use the EXT4 file system, use at least version 2.6.28 of the Linux Kernel.
- On Red Hat Enterprise Linux and CentOS, use at least version 2.6.18-194 of the Linux Kernel.
- XFS is a high-performance filesystem that is optimized for large files and high-throughput workloads.
- XFS supports the preallocation technique used by MongoDB to efficiently allocate space for new files and data writes.
- XFS also supports the noatime mount option, which disables the update of access time for files. This can improve performance by reducing the number of disk writes required for file access.


Overall, the combination of the WiredTiger storage engine with XFS filesystem provides high performance and efficient storage for MongoDB workloads, especially in write-heavy scenarios.




## Need more support from Percona?
Subscribe to Percona Platform to get database support with guaranteed SLAs or proactive database management services from the Percona team.

[Learn more :fontawesome-solid-paper-plane:](https://per.co.na/subscribe){ .md-button }