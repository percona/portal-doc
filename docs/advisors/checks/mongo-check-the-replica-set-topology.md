# Check the Replica Set Topology

## Description
This advisor returns a warning if the replica set has less than 3 members.


## Resolution
Add at least one data-bearing member to the replica set. 

This kind topology assures High Availability and resilience in the case of the network partitioning (“split brain” condition).

## Need more support from Percona?
Subscribe to Percona Platform to get database support with guaranteed SLAs or proactive database management services from the Percona team.

[Learn more :fontawesome-solid-paper-plane:](https://per.co.na/subscribe){ .md-button }