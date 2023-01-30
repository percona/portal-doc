# Index size is larger than data size

## Description
InnoDB uses clustered PRIMARY KEY indexes, hence the PK is appended to the end of all the secondary indexes. 

This means that a large primary key can make the overall index size larger than the actual data.

In addition, redundant indexes can make index data larger than the raw data. Generally, when  index data is larger than actual data, you should review tables since this is due to: 
- poor indexing
- redundant indexes
- large (or composite) PK


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

 In some cases, this is unavoidable, but keeping indexes small and not over-indexing tables is very important when it comes to data design.

## Need help with this?

[Ask a Percona Expert :fontawesome-solid-paper-plane:](https://www.percona.com/about-percona/contact?utm_source=pmm&utm_medium=banner&utm_campaign=advisors_readmore){ .md-button }
