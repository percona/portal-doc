# MySQL binary logs automatically removed too quickly

## Description
Checks that binary logs are kept for at least one day before being purged.
For more information, see the [MySQL documentation](https://dev.mysql.com/doc/refman/8.0/en/replication-options-binary-log.html#sysvar_binlog_expire_logs_seconds).


## Rule
```
For MySQL/PS 5.7 and MariaDB
Check  if expire_logs_days >= 1
For MySQL/PS 8.0 
Check if binlog_expire_logs_seconds >= 86400 
OR binlog_expire_logs_seconds = 0 and expire_logs_days > 1
```

## Resolution
Consider increasing binlog retention period by increasing **binlog_expire_logs_seconds/expire_logs_days**.

## Need help with this?

[Ask a Percona Expert :fontawesome-solid-paper-plane:](https://www.percona.com/about-percona/contact?utm_source=pmm&utm_medium=banner&utm_campaign=advisors_readmore){ .md-button }
