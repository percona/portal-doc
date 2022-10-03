# Warnings not being logged

## Description
Ignoring warnings from being printed on the error.log might result in some important messages being ignored.
For more information, see [log_error_verbosity]( https://dev.mysql.com/doc/refman/8.0/en/server-system-variables.html#sysvar_log_error_verbosity) in the MySQL documentation.

## Rule
```
For MySQL/PS
Check  if log_error_verbosity < 2
For MariaDB
Check if log_warnings < 2:
```

## Resolution
To avoid ignoring warnings from being printed on the error.log, consider setting **log_error_verbosity** to a value of 2 or larger. For MariaDB, use **log_warnings >= 2** .
