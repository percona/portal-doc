# Index size is larger than data size

## Description

InnoDB uses clustered PRIMARY KEY indexes, which adds the primary key to the end of all secondary indexes.

This action can make the overall index size, when it contains a large primary key, larger than the actual data. Redundant indexes can also make an index larger than the raw data. 

Generally, when an index data is larger than actual data, review tables since this may be caused by one of the following:

* poor indexing

* redundant indexes

* large (or composite) PK


## Rule

`SELECT concat(table_name, '.', table_schema) as tbl_name,
          concat(round(table_rows/1000000,2),'M') num_rows,
          concat(round(data_length/(1024*1024*1024),2),'G') data_size,
          concat(round(index_length/(1024*1024*1024),2),'G') idx_size,
          concat(round((data_length+index_length)/(1024*1024*1024),2),'G') total_size,
          round(index_length/data_length,2) idxfrac
          FROM information_schema.TABLES
          WHERE table_schema not in ('information_schema', 'mysql', 'performance_schema', 'sys')
          ORDER BY data_length+index_length DESC
          LIMIT 10`

## Resolution

Review tables for redundant indexes or large primary keys.

In some cases, this size is unavoidable, but small indexes and not over-indexing tables is important in data design.

## Need more support from Percona?

Subscribe to Percona Platform to get database support with guaranteed SLAs or proactive database management services from the Percona team.

[Learn more :fontawesome-solid-paper-plane:](https://per.co.na/subscribe){ .md-button }
