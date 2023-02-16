# Master not verifying checksums

## Description
Having master_verify_checksum disabled will inhibit checksum of binary log events, thus allowing a corrupt event to be replicated, which will consequently cause data to divert on the replica, or replication to fail altogether due to corrupt events.
For more information, see [master_verify_checksum in the MuSQL documentation](https://dev.mysql.com/doc/refman/8.0/en/replication-options-binary-log.html#sysvar_master_verify_checksum)

## Rule
`SELECT IF(@@global.master_verify_checksum=1, 1, 0)  as master_verify_checksum_enabled`

## Resolution
Consider setting **master_verify_checksum=1** to avoid corrupt binlogs and the chance of breaking replication or silently introducing differences in the replicas.

## Need more support from Percona?
Subscribe to Percona Platform to get database support with guaranteed SLAs or proactive database management services from the Percona team.

[Learn more :fontawesome-solid-paper-plane:](https://per.co.na/subscribe){ .md-button }
