# Check for relations with high number of indexes


## Description

This check will scan all databases in the cluster and list relations with more than 10 indexes.


## Resolution

Connecting to a database and running the query:

```
SELECT current_database() AS datname, relname, count(*) AS idxcount FROM pg_stat_user_indexes GROUP BY 1,2 ORDER BY 3 DESC
```
Relations with a high number of indexes may or not be needed. Therefore, it is advisable to check if the indexes are being used or not. Having unnecessary indexes can result in unwanted performance issues and overhead due to the maintenance of the index.  



## Need more support from Percona?

Subscribe to Percona Platform to get database support with guaranteed SLAs or proactive database management services from the Percona team.

[Learn more :fontawesome-solid-paper-plane:](https://per.co.na/subscribe){ .md-button }
