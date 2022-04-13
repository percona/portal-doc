# MySQL check binlog sync status

## Description
Flushing transactions to disk does not guarantee that binary logs are flushed as well. 

This means that on a crash, there might be transactions applied to the instance’s data which the instance has no binlog for.

For more information, see the [MySQL documentation](https://dev.mysql.com/doc/refman/5.7/en/replication-options-binary-log.html#sysvar_sync_binlog)
and [Percona blog posts on the topic](https://www.percona.com/blog/2018/05/04/how-binary-logs-and-filesystems-affect-mysql-performance/).

## Rule
`SELECT @@global.sync_binlog;`

## Resolution
Disable localhost bypass:
1. Edit mongod.conf and set the following parameter:
        *setParameter:
           enableLocalhostAuthBypass: false*


2. Perform a rolling restart of your mongod nodes to apply the changes.
