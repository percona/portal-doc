# PostgreSQL stale replication slot

## Description

Stale replication slots lead to WAL file accumulation. This can result in a database server outage.

A stale replication slot is a slot that satisfies the following criteria:

- Not a temporary slot.
- Not an active slot.
- WAL distance between current WAL position and slot’s restart log sequence number is more than the current setting for the `max_wal_size` configuration option.

## Resolution

Review the output of the `SELECT * FROM pg_replication_slots` query and identify the slots that are inactive and have an old `restart_lsn`. 

Drop such slots as soon as possible. You can recreate the slot, but note that the receiving end might need to be re-synchronized.

## Need more support from Percona?
Subscribe to Percona Platform to get database support with guaranteed SLAs or proactive database management services from the Percona team.

[Learn more :fontawesome-solid-paper-plane:](https://per.co.na/subscribe){ .md-button }