# MongoDB Versions
## Description
This check returns the MongoDB or Percona Server for MongoDB versions currently used in your environment. It also provides information on other available minor or major versions to consider for upgrades.

## Resolution
If you are running PSMDB/MongoDB version lower than the latest minor/major patch, then we recommend upgrading to the latest version in a stepped manner. Do not skip a major version release. 

1. Upgrade to the latest minor patch of the current version. - This will fix all the bugs/changes in that specific version.
2. Then you can plan Major version upgrades in a stepped manner. It is recommended to upgrade to the latest major patch once it has become stable.

## Recommended Upgrade Process:
Recommendation is to follow an upgrade path similar to this: 
- Current minor version: 4.2.23
- Desired version: 5.0.14
- Recommended Upgrade Path: 4.2.23 => 4.4.18 => 5.0.14.
- Do NOT skip over the major version 4.4.x on the way to major version 5.0.x


> **Important**
> 
>Before performing any major upgrades on the Production environment: 
>- Always test the newer version first in the lower environment(dev, staging) and verify the compatibility of that version with your application.
>- Make sure the Drivers are compatible with the newer version.


If you are running **Percona Server for MongoDB (PSMDB)**, then follow the below link for minor/major upgrades of a 
ReplicaSet or Sharded cluster - [Upgrade Procedure for PSMDB](https://www.percona.com/blog/upgrade-process-of-percona-server-for-mongodb-replica-set-and-shard-cluster/)

If you are running **MongoDB**, then follow the below link for minor/major upgrades of a 
ReplicaSet or Sharded cluster - [Upgrade Procedure for MongoDB](https://www.mongodb.com/docs/manual/tutorial/upgrade-revision/)

## Need more support from Percona?
Subscribe to Percona Platform to get database support with guaranteed SLAs or proactive database management services from the Percona team.

[Learn more :fontawesome-solid-paper-plane:](https://per.co.na/subscribe){ .md-button }