# MongoDB replica set topology

## Description
This advisor warns if the Replica Set cluster has less than three members.

## Resolution
Add at least another data-bearing member. This kind of topology ensures High Availability and resilience in case of network partitioning (“split-brain” condition).

## Need help with this?

[Ask a Percona Expert :fontawesome-solid-paper-plane:](https://www.percona.com/about-percona/contact?utm_source=pmm&utm_medium=banner&utm_campaign=advisors_readmore){ .md-button }
