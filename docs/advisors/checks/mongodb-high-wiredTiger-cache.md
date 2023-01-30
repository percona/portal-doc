# Check wiredTiger cache size

## Description
This advisor check warns if the configured wired tiger cache size is greater than 50% of server memory. 

This is important because MongoDB uses remaining available memory (FS cache) beyond its own storage engine cache to maintain connections, aggregation/sort operations, cursors etc. 

Keeping non-default high cache size for wiredtiger can cause OOM issues.

To avoid performance issues, see the [WiredTiger Storage Engine blog](https://www.mongodb.com/docs/manual/core/wiredtiger/#memory-use) to check & set the right value for your environment.


## Rule
```
METRICS_INSTANT
# to fetch the value
node_memory_numa_MemTotal{node_name="{{.NodeName}}"}

METRICS_INSTANT
# to fetch the value
mongodb_ss_wt_cache_maximum_bytes_configured{service_name="{{.ServiceName}}"}            
```

## Resolution
- Let mongod use default cache size of 50% of (RAM - 1 GB), OR 
- Make sure that **storage.wiredTiger.engineConfig.**cacheSizeGB** in the configuration file doesn’t exceed 50% of the server memory.

## Need help with this?

[Ask a Percona Expert :fontawesome-solid-paper-plane:](https://www.percona.com/about-percona/contact?utm_source=pmm&utm_medium=banner&utm_campaign=advisors_readmore){ .md-button }