# Check for enabled minimal logging features of PostgreSQL


## Description
This check provides feedback on enabled logging features and is strictly recommended to help identify potential issues when reviewing the database cluster and log files. 

## Resolution

Enabling the following logging parameters will help when troubleshooting database performance issues.

**Logging_collector**

Enables the logging collector which captures log messages sent to the stderr and redirects them into log files.

**log_temp_files**

Enables logging of temporary file creation and the queries generating them. This is useful when trying to size work_mem or other related parameters.  Extremely useful when parsing log files with a tool such as pg_badger.

**Note: If your running cluster is generating large amounts of temporary files, this could consume disk space rapidly. Consider setting a value which will log temporary files of x size.**

**log_check_points**

Logs statistics about checkpoints and when they occur. 

**log_min_duration_statement**

This is useful for determining slow running queries. Setting a value in milliseconds will log queries that take either the set value or longer time to complete.



## Need more support from Percona?

Subscribe to Percona Platform to get database support with guaranteed SLAs or proactive database management services from the Percona team.

[Learn more :fontawesome-solid-paper-plane:](https://per.co.na/subscribe){ .md-button }
