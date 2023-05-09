# MongoDB sharding - chunk imbalance across shards

## Description
This check warns if the chunks are imbalanced across shards.


In a sharded cluster, chunk imbalances can occur when the data is not evenly distributed among the shards. This can lead to some shards having more chunks than others. This can cause performance issues and slower query times.

There are a few possible reasons for chunk imbalance:

- **Poor shard key selection:** If the shard key is not chosen properly, some shards may end up with a larger portion of the data than others. For example, if the shard key is based on a timestamp and the data is inserted in a sequential manner, this can create hotspots due to busier application write periods. 

- **Jumbo chunks:** Jumbo chunks can be another cause of chunk imbalances in a sharded cluster . Jumbo chunks are chunks that have grown beyond the maximum size that is allowed by MongoDB. When a chunk becomes jumbo, MongoDB cannot split it further automatically and the balancer won’t distribute the associated data across the shards. Jumbo chunks are often caused by low cardinality or too high frequency of elements in a shard key.

## Resolution

To address chunk imbalance, you can:

- **Select a good shard key:** 
The choice of shard key affects the creation and distribution of chunks across the available shards. While selecting the shard key, consider below points:

1. High Cardinality.
2. Non-monotonic is nature.
3. It should be used in most of your queries.
4. Reads should be done from particular shards.
5. Writes should get written across all shards.

Starting in MongoDB 5.0, you can reshard a collection by changing a collection's shard key. Follow the [MongoDB Documentation](https://www.mongodb.com/docs/manual/core/sharding-reshard-a-collection/#std-label-sharding-resharding) on how to change the shard key.

- **Clear the jumbo chunks:**
To prevent the situation described above, we should check for jumbo chunks and remove the jumbo flag. Kindly refer to the [blog](https://www.percona.com/blog/finding-undetected-jumbo-chunks-in-mongodb/) on how to detect the jumbo chunks and split them.



## Need more support from Percona?
Subscribe to Percona Platform to get database support with guaranteed SLAs or proactive database management services from the Percona team.

[Learn more :fontawesome-solid-paper-plane:](https://per.co.na/subscribe){ .md-button }