# InnoDB redo log size advisor
## Description
The configuration variable innodb_log_file_size is one of the most important settings with respect to innodb configuration.
The rule of the thumb is to keep one hour of traffic in those logs and let the checkpointing perform its work as smoothly as possible. If you don't do this, InnoDB will do synchronous flushing at the worst possible time, i.e. when you are busiest.
This check will raise a warning if data written are more than the configured redo log size but it will raise an error if InnoDB has uncheckpointed data reaching more than 80% of InnoDB checkpoint age. As above this point the async flushing stops and InnoDB starts synchronous flushing creating degraded performance.

## Resolution
Upon Warning, review the innodb_log_file_size and reason that caused the spike. 
Upon Error, revise the innodb_log_file_size.


## Need more support from Percona?
Subscribe to Percona Platform to get database support with guaranteed SLAs or proactive database management services from the Percona team.

[Learn more :fontawesome-solid-paper-plane:](https://per.co.na/subscribe){ .md-button }
