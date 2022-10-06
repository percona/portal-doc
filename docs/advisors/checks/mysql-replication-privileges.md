# Replication privileges

## Description
Replicas connect to Source with a specific user. This user to efficiently and safely execute the replication require ONLY the REPLICATION SLAVE Grant. 
At the same time a standard user, should not have REPLICATION SLAVE as grant and instead use the REPLICATION CLIENT grant to access replication iformation.
The check identify and reports the list of users who have REPLICATION SLAVE as assigned grants in conjunction with other grants. 

## Rule
```
Select @@hostname service_name,version,count(user) nuser, group_concat(user SEPARATOR '; ')users, reason from(select @@version version, 1 found, concat(user,'@',host) user,plugin, 1 reason from mysql.user where Repl_slave_priv='Y'AND (Select_priv = 'Y' OR Insert_priv  = 'Y' OR Update_priv = 'Y' OR Delete_priv = 'Y' OR Create_priv = 'Y' OR Drop_priv = 'Y' OR Reload_priv = 'Y' OR Shutdown_priv = 'Y' OR Process_priv = 'Y' OR File_priv = 'Y' OR Grant_priv = 'Y' OR References_priv = 'Y' OR Index_priv = 'Y' OR Alter_priv = 'Y' OR Show_db_priv = 'Y' OR Super_priv = 'Y' OR Create_tmp_table_priv = 'Y' OR Lock_tables_priv = 'Y' OR Execute_priv = 'Y' OR Repl_client_priv = 'Y' OR Create_view_priv = 'Y' OR Show_view_priv = 'Y' OR Create_routine_priv = 'Y' OR Alter_routine_priv = 'Y' OR Create_user_priv = 'Y' OR Event_priv = 'Y' OR Trigger_priv = 'Y' OR Create_tablespace_priv = 'Y')) as tt group by reason,service_name,version  order by reason;    
Select  user,host,IF(channel_name='','NA',channel_name) as channel from performance_schema.replication_connection_configuration;
```

## Resolution
Revoke the REPLICATION SLAVE from standard user, or any additional grant from the replication user.

IE:
```
>show grants for replica@'%';
+---------------------------------------------------------------------+
| Grants for replica@%                                                |
+---------------------------------------------------------------------+
| GRANT REPLICATION SLAVE, REPLICATION CLIENT ON *.* TO `replica`@`%` |
+---------------------------------------------------------------------+

>revoke REPLICATION CLIENT on *.* from 'replica'@'%';
Query OK, 0 rows affected (0.10 sec)
```