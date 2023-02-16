# Check mongodb localhost bypass

## Description
This advisor returns a warning if MongoDB **enableLocalhostAuthBypass** parameter is set to True.

This represents a security vulnerability and should be disabled.

For more information, see the [MongoDB documentation](https://docs.mongodb.com/manual/reference/parameters/#mongodb-parameter-param.enableLocalhostAuthBypass).

## Rule
```
MONGODB_GETPARAMATER
db.adminCommand({'getParameter':'*'}).enableLocalhostAuthBypass
true

            enableLocalhostAuthBypass = docs[0]["enableLocalhostAuthBypass"]
            print(repr(enableLocalhostAuthBypass))
            if enableLocalhostAuthBypass == "true":
```


## Resolution
Follow the steps below to disable localhost bypass:
1. Edit mongod.conf and set the below parameter.
```
setParameter:
  enableLocalhostAuthBypass: false
```
2. Roll-restart your mongod nodes to apply the changes.
   
## Need more support from Percona?
Subscribe to Percona Platform to get database support with guaranteed SLAs or proactive database management services from the Percona team.

[Learn more :fontawesome-solid-paper-plane:](https://per.co.na/subscribe){ .md-button }

