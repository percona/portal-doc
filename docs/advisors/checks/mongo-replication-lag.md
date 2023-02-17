# MongoDB Replication Lag	

## Description
This check returns a warning if a secondary member of the Replica Set lags more than ten seconds behind the primary one. This interval is the default threshold where flow control engages.


## Resolution
[MongoDB documentation](https://www.mongodb.com/docs/manual/tutorial/troubleshoot-replica-sets/#replication-lag-causes), specifies the following possible causes of replication lag:

- **Network latency**

    Check the network routes between the members of your set to ensure that there is no packet loss or network routing issue.
    Use tools like **ping** to test latency between set members, and **traceroute** to expose the routing of packets network endpoints.

- **Disk throughput**
  
    If the file system and disk device on the secondary member is unable to flush data to disk as quickly as the primary one, the secondary will have difficulty keeping state. 
    Disk-related issues are incredibly prevalent on multi-tenant systems, including virtualized instances, and can be transient if the system accesses disk devices over an IP network (as is the case with Amazon's EBS system.)

    Use system-level tools to assess disk status, including **iostat** or **vmstat**.

- **Concurrency**

    In some cases, long-running operations on the primary member can block replication on secondaries. For best results, configure Write concern to require confirmation of replication to secondaries. This prevents Write operations from returning if replication cannot keep up with the Write load.

    You can also use the database profiler to see if there are slow queries or long-running operations that correspond to the incidences of lag.

- **Appropriate Write Concern**
  
    If you are performing a Large Data Ingestion or Bulk Load operation that require a large number of writes to the primary, particularly with unacknowledged Write Concern, the secondaries will not be able to read the oplog fast enough to keep up with changes.

    To prevent this, request Write acknowledgement Write Concern after every 100, 1000, or another interval to provide an opportunity for secondaries to catch up with the primary.



## Need more support from Percona?
Subscribe to Percona Platform to get database support with guaranteed SLAs or proactive database management services from the Percona team.

[Learn more :fontawesome-solid-paper-plane:](https://per.co.na/subscribe){ .md-button }
