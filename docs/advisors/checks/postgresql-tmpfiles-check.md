# PostgreSQL temporary files written to disk check
## Description
Details about the temporary files and total space used are reported. This information can be utilized to fine tune the work_mem parameter.


## Resolution
There are numerous tunable parameters which can affect the number of temporary files created. However, the work_mem parameter which defaults to 4MB is the most commonly targeted parameter which sets the base maximum amount of memory to be used by a query operation (such as a sort or hash table) before writing to temporary disk files.

For a complex query, several sort or hash operations might be running in parallel; each operation will generally be allowed to use as much memory as this value specifies before it starts to write data into temporary files. Also, several running sessions could be doing such operations concurrently. Therefore, the total memory used could be many times the value of work_mem; it is necessary to keep this fact in mind when choosing the value. Sort operations are used for ORDER BY, DISTINCT, and merge joins. Hash tables are used in hash joins, hash-based aggregation, and hash-based processing of IN subqueries.

## Need more support from Percona?
Subscribe to Percona Platform to get database support with guaranteed SLAs or proactive database management services from the Percona team.

[Learn more :fontawesome-solid-paper-plane:](https://per.co.na/subscribe){ .md-button }
