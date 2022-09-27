# MySQL binlog row image set to MINIMAL
## Description
Having binlog_row_image set to MINIMAL, while it significantly reduce the amount of data pushed into the binlog, it also skip essential data that can be used to recover your database from data corruption, or human mistakes.

Setting the server with:
```
binlog_format=ROW
binlog_row_image =FULL
```
Will increase the size of the binary logs but at the same time will provide you a way to recover old data.

See also: 

[flashback](https://mydbops.wordpress.com/2019/05/22/flashback-recovery-in-mariadb-mysql-percona/)

[MySQL manual](https://dev.mysql.com/doc/refman/8.0/en/replication-options-binary-log.html#sysvar_binlog_row_image)

However, setting the `binlog_row_image` to FULL can result in a significant increase of data if you use many and large BLOB/TEXT columns that don't change often.  
Because this while best practice is to use FULL, there are cases as the one above where using MINIMAL is perfectly fine and preferable.

## Rule
`SELECT IF(@@global.binlog_row_image='MINIMAL', 1, 0);`


## Resolution
Please consider setting binlog_row_image=FULL to reduce the footprint of your binary logs on disk.
