# MySQL binlog row image set to MINIMAL
## Description
Setting **binlog_row_image** to MINIMAL significantly reduces the amount of data pushed into the binlog. However, this will also skip essential data that can be used to recover your database from data corruption, or human mistakes.

Setting the server with:
```
binlog_format=ROW
binlog_row_image =FULL
```
will increase the size of the binary logs, but at the same time will provide you a way to recover old data.

For more information, see [flashback recovery](https://mydbops.wordpress.com/2019/05/22/flashback-recovery-in-mariadb-mysql-percona/) and the [MySQL manual](https://dev.mysql.com/doc/refman/8.0/en/replication-options-binary-log.html#sysvar_binlog_row_image).

On the other side, setting the `binlog_row_image` to FULL can result in a significant increase of data if you use many and large BLOB/TEXT columns that don't change often.  
Therefore, although best practice recommends using FULL, in some cases (like the one above) using MINIMAL is perfectly fine.

## Rule
`SELECT IF(@@global.binlog_row_image='MINIMAL', 1, 0);`

## Resolution
Consider setting **binlog_row_image=FULL** to increase the chances of successful data recovery.

## Need help with this?

[Ask a Percona Expert :fontawesome-solid-paper-plane:](https://www.percona.com/about-percona/contact?utm_source=pmm&utm_medium=banner&utm_campaign=advisors_readmore){ .md-button }
