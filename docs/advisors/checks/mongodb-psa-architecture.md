# MongoDB PSA Architecture

## Description
This check returns an error if the replicaSet is using a PSA architecture.

## Resolution

A replica set can be configured with either a PSS (Primary-Secondary-Secondary) or a PSA (Primary-Secondary-Arbiter) architecture.

In a three-member replica set with a primary-secondary-arbiter (PSA) architecture or a sharded cluster with three-member PSA shards, the arbiter does not hold a copy of the data. These deployments provide only one complete copy of the data. They are used primarily for situations where nodes are located in different Data Centers and you want to preserve quorum in cases where you want to avoid split brain caused by potential network issues.

Arbiters require fewer resources and can thus provide lower cost for the cluster. However, using a PSA architecture reduces the redundancy and fault tolerance that MongoDB has built-in natively. It is not recommended to use PSA (Primary-Secondary-Arbiter) architecture in Production environments due to below **serious concerns.**

**Data Redundancy**
**Fault Tolerance**

If a Secondary node is down in a PSA architecture, the replica set is left  with only one Primary & one arbiter.  Since an Arbiter is not a full data-bearing node, this causes some serious operational consequences listed below:

- Until you have a second data-bearing member online, data redundancy is compromised and writes can only be acknowledged by the current primary.

- You no longer have active replication. If your secondary is offline for too long, it may fall off the oplog and need to be re-synced.

- If you have lost your initial Primary and have failed over to your Secondary as the new Primary, you will not have Redundancy or Fault tolerance again until the former Primary has fully resynced. If anything happens to the new Primary during that recovery time, you are left without a good node since the arbiters are non-data-bearing. This can result in data loss and application downtime.

- Applications and internal processes can no longer use a majority write concern. If you haven't planned for this, writes requesting majority acknowledgement may block until a majority of data bearing members are available or a timeout is reached (if set for the write command). If your replica set is part of a sharded cluster, this can also prevent successful chunk migrations between shards.

- Applications and internal processes will not see the newest data on the primary using a majority read concern. Some features (for example, change streams in MongoDB 3.6+) rely on reading majority committed data to avoid the chance that changes may be rolled back. If the majority commit point cannot be advanced, there will also be increased pressure on the WiredTiger cache.

The above consequences can be avoided by having a Primary-Secondary-Secondary (PSS) configuration.  For Production systems it is highly recommended to use a PSS architecture.


## Need more support from Percona?
Subscribe to Percona Platform to get database support with guaranteed SLAs or proactive database management services from the Percona team.

[Learn more :fontawesome-solid-paper-plane:](https://per.co.na/subscribe){ .md-button }
