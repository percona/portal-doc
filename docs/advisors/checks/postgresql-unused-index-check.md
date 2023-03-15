# Check for relations with unused indexes for PostgreSQL


## Description

This check scans all databases in the cluster and lists relations with indexes that have not been used since the last statistics reset.


## Resolution

Connect to a database and run the query:

```
SELECT * FROM pg_stat_user_indexes 
```

The output lists the indexes for the current database. The column idx_scan indicates how many times the index has been used.

If you find indexes which have not been used, one should re-evaluate the need of the index and take appropriate action.  Keep in mind that some indexes may be needed to address foreign key performance. For example deleting or updating a key would force postgres to validate the constraint. Without an index, this could result in sequential scans. 


## Need more support from Percona?

Subscribe to Percona Platform to get database support with guaranteed SLAs or proactive database management services from the Percona team.

[Learn more :fontawesome-solid-paper-plane:](https://per.co.na/subscribe){ .md-button }
