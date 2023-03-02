# Replication privileges

## Description

The `REPLICATION_SLAVE` privileges enable a user account to connect from a replica to a replication source server.

A standard user should not be granted `REPLICATION SLAVE` but instead be granted the `REPLICATION CLIENT` to access replication information.

The check lists the users assigned the `REPLICATION SLAVE` grant along with other grants.

## Rule

```sql
Select @@hostname service_name,version,count(user) nuser, group_concat(user SEPARATOR '; ')users, reason from(select @@version version, 1 found, concat(user,'@',host) user,plugin, 1 reason from mysql.user where Repl_slave_priv='Y'AND (Select_priv = 'Y' OR Insert_priv  = 'Y' OR Update_priv = 'Y' OR Delete_priv = 'Y' OR Create_priv = 'Y' OR Drop_priv = 'Y' OR Reload_priv = 'Y' OR Shutdown_priv = 'Y' OR Process_priv = 'Y' OR File_priv = 'Y' OR Grant_priv = 'Y' OR References_priv = 'Y' OR Index_priv = 'Y' OR Alter_priv = 'Y' OR Show_db_priv = 'Y' OR Super_priv = 'Y' OR Create_tmp_table_priv = 'Y' OR Lock_tables_priv = 'Y' OR Execute_priv = 'Y' OR Repl_client_priv = 'Y' OR Create_view_priv = 'Y' OR Show_view_priv = 'Y' OR Create_routine_priv = 'Y' OR Alter_routine_priv = 'Y' OR Create_user_priv = 'Y' OR Event_priv = 'Y' OR Trigger_priv = 'Y' OR Create_tablespace_priv = 'Y')) as tt group by reason,service_name,version  order by reason;    
Select  user,host,IF(channel_name='','NA',channel_name) as channel from performance_schema.replication_connection_configuration;
```

## Resolution

Revoke `REPLICATION SLAVE` from a standard user or any additional grant from the replication user.

For example, to see the assigned grants for a replica and to revoke a grant:

```sql
mysql> SHOW GRANTS for replica@'%';
+---------------------------------------------------------------------+
| Grants for replica@%                                                |
+---------------------------------------------------------------------+
| GRANT REPLICATION SLAVE, REPLICATION CLIENT ON *.* TO `replica`@`%` |
+---------------------------------------------------------------------+

mysql> REVOKE REPLICATION SLAVE on *.* from 'replica'@'%';
Query OK, 0 rows affected (0.10 sec)
```

## Need more support from Percona?

Subscribe to Percona Platform to get database support with guaranteed SLAs or proactive database management services from the Percona team.

[Learn more :fontawesome-solid-paper-plane:](https://per.co.na/subscribe){ .md-button }
