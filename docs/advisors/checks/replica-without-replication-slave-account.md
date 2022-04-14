# Replica without replication slave account

## Description
If the master ever fails, you may want to use one of the slaves as the new master. An account with the REPLICATION SLAVE privilege must exist for a server to act as a replication master (so a slave can connect to it).

Therefore, it is a good idea to create this account on your slaves to prepare it to take over for a master if needed.

## Rule
`select IF(count(User)> 0,1,0) from mysql.user where Repl_slave_priv='Y';`

## Resolution
Create a replication user like CREATE USER 'replication'@'192.168.0.%' IDENTIFIED BY 'password'; and grant ‘REPLICATION SLAVE’ to it. 