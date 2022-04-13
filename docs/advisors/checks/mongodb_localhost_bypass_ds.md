## MongoDB Localhost bypass check

This check returns a warning if MongoDB **enableLocalhostAuthBypass** parameter is set to True.
This represents a security vulnerability and should be disabled. For more information, see the [MongoDB documentation](https://docs.mongodb.com/manual/reference/parameters/#mongodb-parameter-param.enableLocalhostAuthBypass). 

## Rule
`SELECT @@global.sync_binlog;`

## Resolution
Consider setting the **sync_binlog** variable to **1** with `SET GLOBAL sync_binlog=1`.


