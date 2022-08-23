# MySQL server replicating events are not logged

## Description
log_replica_updates specifies whether updates received by a replica server from a replication source server should be logged to the replica's own binary log.

Enabling this variable causes the replica to write the updates that are received from a source and performed by the replication SQL thread to the replica's own binary log. Binary logging, which is controlled by the --log-bin option and is enabled by default, must also be enabled on the replica for updates to be logged. See Section 17.1.6, “Replication and Binary Logging Options and Variables”. log_replica_updates is enabled by default, unless you specify --skip-log-bin to disable binary logging, in which case MySQL also disables replica update logging by default. If you need to disable replica update logging when binary logging is enabled, specify --log-replica-updates=OFF at replica server startup.

Enabling log_replica_updates enables replication servers to be chained. For example, you might want to set up replication servers using this arrangement:
A -> B -> C

Here, A serves as the source for the replica B, and B serves as the source for the replica C. For this to work, B must be both a source and a replica. With binary logging enabled and log_replica_updates enabled, which are the default settings, updates received from A are logged by B to its binary log, and can therefore be passed on to C.


## Rule
```
if name == "log_replica_updates" or name == "log_slave_updates":
   if value == "OFF":
```

## Resolution
Change the configuration setting:
Log_replica_updates = 1 

!! Warning this parameter is NOT dynamic server restart is needed !!
