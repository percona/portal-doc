# MySQL General log is active

## Description
The general log contains every single query that is hitting the database. These queries are logged before execution. 

Enabling the general log can seriously impact disk space and overall performance. 


## Rule
`SELECT @@global.general_log;`


## Resolution
Turn off the **general_log** in the configuration file and restart the instance. 

## Need more support from Percona?
Subscribe to Percona Platform to get database support with guaranteed SLAs or proactive database management services from the Percona team.

[Learn more :fontawesome-solid-paper-plane:](https://per.co.na/subscribe){ .md-button }
