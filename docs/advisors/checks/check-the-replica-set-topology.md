# MongoDB replica set topology

## Description
This advisor warns if the Replica Set cluster has less than three members.

## Resolution
Add at least another data bearing member. This kind topology assures High Availability and resilience in the case of the network partitioning (“split brain” condition).

