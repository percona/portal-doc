# MongoDB replica set topology
## Description
This check returns a warning if the Replica Set cluster has less than three members.

## Resolution
It is recommended that a Replica Set cluster has at least three data-bearing members. 

This kind topology assures High Availability and resilience in the case of the network partitioning (“split brain” condition).
