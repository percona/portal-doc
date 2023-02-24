# mysql_configuration_max_connections_usage
## Description
The status variable "max_used_connections" indicates the highest number of connections utilized since the previous system restart. If this value approaches the predetermined "max_connections" limit, it warrants attention.


## Resolution
Revisit the max_connections configuration option and revise it inside the limit of your platform resources, if necessary. Alternatively manage your max connection usage.

## Need more support from Percona?
Subscribe to Percona Platform to get database support with guaranteed SLAs or proactive database management services from the Percona team.

[Learn more :fontawesome-solid-paper-plane:](https://per.co.na/subscribe){ .md-button }
