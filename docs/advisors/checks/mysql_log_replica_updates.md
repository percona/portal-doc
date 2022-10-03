# MySQL server replicating events are not logged

## Description
**log_replica_updates** specifies whether updates received by a replica server from a replication source server should be logged to the replica's own binary log.

When this variable is enabled, the replica writes to the replica's own binary log all the updates received from a source and performed by the replication SQL thread. 

To ensure that updates are logged, make sure that binary logging is also enabled on the replica. This is controlled by the **--log-bin** option and is enabled by default.  
For more information, see [Replication and Binary Logging Options and Variables](https://dev.mysql.com/doc/refman/8.0/en/replication-options.html).

**log_replica_updates** is enabled by default, unless you specify **--skip-log-bin** to disable binary logging. In this case MySQL also disables replica update logging by default.
If you need to disable replica update logging when binary logging is enabled, specify **--log-replica-updates=OFF** at replica server startup.

Enabling **log_replica_updates** enables replication servers to be chained. For example, you might want to set up replication servers using this arrangement: A -> B -> C

Here, A serves as the source for the replica B, and B serves as the source for the replica C. For this to work, B must be both a source and a replica. 
With binary logging enabled and **log_replica_updates** enabled (default settings), updates received from A are logged by B to its binary log, and can therefore be passed on to C. 


## Rule
```
if name == "log_replica_updates" or name == "log_slave_updates":
   if value == "OFF":
```

## Resolution
Change the configuration setting:
**Log_replica_updates = 1** 


!!! warning alert alert-success "Warning"
     This parameter is NOT dynamic and server restart is needed.