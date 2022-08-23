# Index size is larger than data size

## Description
InnoDB uses clustered PRIMARY KEY indexes (meaning the PK is appended to the end of all the secondary indexes).  This means that a
large primary key can make the overall index size larger than the actual data.  Additionally, redundant indexes can cause the index
data to be larger than the raw data.  In general, cases where index data is larger than actual data is a sign of poor indexing, 
redundant indexes, or a large (or composite) PK and those tables should be reviewed. 


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
Review tables for redundant indexes or large primary keys.  In some cases, this is unavoidable, but keeping indexes small and not overindexing tables is very important when it comes to data design.