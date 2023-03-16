# Settings changed on a instance that requires a restart

## Description

This check notifies when one or several parameter settings require a server restart/reload following a recent change.

## Resolution

Use the query below to check the parameters:

```sql
SELECT name, setting, short_desc, reset_val FROM pg_settings WHERE pending_restart IS true;
```

Restart the PostgreSQL server to apply the new value.

## Need more support from Percona?
Subscribe to Percona Platform to get database support with guaranteed SLAs or proactive database management services from the Percona team.

[Learn more :fontawesome-solid-paper-plane:](https://per.co.na/subscribe){ .md-button }
