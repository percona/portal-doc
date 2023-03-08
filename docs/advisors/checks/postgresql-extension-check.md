# PostgreSQL outdated extensions

## Description

It is common for installed extensions to follow upgrades of PostgreSQL. However, upgrading to a newer version of Postgres does not automatically upgrade the installed extensions. In some cases this is overlooked and is acceptable. However, one could be missing out on improvements, features and compatibility with newer versions of Postgres. Therefore, it is advisable to stay current with the latest extension if they have been validated by your development team.

## Resolution

Upgrading an extension is straightforward. A simple query is executed from within the database containing the extension.

 ALTER EXTENSION extension_name UPDATE TO ‘version’;


## Need more support from Percona?

Subscribe to Percona Platform to get database support with guaranteed SLAs or proactive database management services from the Percona team.

[Learn more :fontawesome-solid-paper-plane:](https://per.co.na/subscribe){ .md-button }
