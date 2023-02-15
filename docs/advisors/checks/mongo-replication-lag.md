# MongoDB Replication Lag	

## Description
This check returns a warning if a secondary member of the Replica Set lag is more than 10 secs, which is the default threshold where flow control engages.


## Resolution
From [MongoDB manual](https://www.mongodb.com/docs/manual/tutorial/troubleshoot-replica-sets/#replication-lag-causes), possible causes of replication lag include:

- Network Latency

Check the network routes between the members of your set to ensure that there is no packet loss or network routing issue.

Use tools including ping to test latency between set members and traceroute to expose the routing of packets network endpoints.

- Disk Throughput

If the file system and disk device on the secondary is unable to flush data to disk as quickly as the primary, then the secondary will have difficulty keeping state. Disk-related issues are incredibly prevalent on multi-tenant systems, including virtualized instances, and can be transient if the system accesses disk devices over an IP network (as is the case with Amazon's EBS system.)

Use system-level tools to assess disk status, including iostat or vmstat.

- Concurrency

In some cases, long-running operations on the primary can block replication on secondaries. For best results, configure write concern to require confirmation of replication to secondaries. This prevents write operations from returning if replication cannot keep up with the write load.

You can also use the database profiler to see if there are slow queries or long-running operations that correspond to the incidences of lag.

- Appropriate Write Concern

If you are performing a large data ingestion or bulk load operation that requires a large number of writes to the primary, particularly with unacknowledged write concern, the secondaries will not be able to read the oplog fast enough to keep up with changes.

To prevent this, request write acknowledgement write concern after every 100, 1000, or another interval to provide an opportunity for secondaries to catch up with the primary.



## Need more support from Percona?
Subscribe to Percona Platform to get database support with guaranteed SLAs or proactive database management services from the Percona team.

[Learn more :fontawesome-solid-paper-plane:](https://per.co.na/subscribe){ .md-button }
