# Check the Replica Set Topology

## Description
This advisor returns a warning if the Replica Set cluster has less than 3 members.



## Rule
```
         if members_number < 3:
```


## Resolution
It is recommended a Replica Set cluster has at least 3 data bearing members. 

This kind topology assures High Availability and resilience in the case of the network partitioning (“split brain” condition).

## Need more support from Percona?
Subscribe to Percona Platform to get database support with guaranteed SLAs or proactive database management services from the Percona team.

[Learn more :fontawesome-solid-paper-plane:](https://per.co.na/subscribe){ .md-button }