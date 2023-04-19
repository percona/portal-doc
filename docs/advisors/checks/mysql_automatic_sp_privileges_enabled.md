# Automatic_sp_privileges configuration for MySQL


## Description

The automatic_sp_privileges when enabled, causes automatic grants or revokes of the EXECUTE and ALTER ROUTINE privileges to the creator of a stored routine upon creation or removal of the routine. This check verifies that the automatic_sp_privileges is ON and alerts otherwise.

## Resolution

Consider setting automatic_sp_privileges to 1 (ON). 


## Need more support from Percona?

Subscribe to Percona Platform to get database support with guaranteed SLAs or proactive database management services from the Percona team.

[Learn more :fontawesome-solid-paper-plane:](https://per.co.na/subscribe){ .md-button }
