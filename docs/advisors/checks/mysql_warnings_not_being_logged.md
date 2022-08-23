# warnings not being logged

## Description
Ignoring warnings from being printed on the error.log might result in some important messages being ignored.
See https://dev.mysql.com/doc/refman/8.0/en/server-system-variables.html#sysvar_log_error_verbosity  for more information

## Rule
```
For MySQL/PS
Check  if log_error_verbosity < 2
For MariaDB
Check if log_warnings < 2:
```

## Resolution
Please consider setting log_error_verbosity to a value of 2 or larger (log_warnings >= 2 for MariaDB) to avoid ignoring warnings from being printed on the error.log
