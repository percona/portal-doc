# Write Tickets during runtime is > 128

## Description
This advisor check warns if the number of write tickets during runtime is more than 128. 

This is relevant because the performance can drop if the number of tickets is too high.
The parameter also needs to be set at the configuration file.

Ideally, the number of tickets should be based on the number of CPU available. 
The default write ticket is 128. This can be adjusted for your mongod and your mongos nodes. 

See [wiredTigerConcurrentWriteTransactions]
(https://docs.mongodb.com/manual/reference/parameters/#mongodb-parameter-param.wiredTigerConcurrentWriteTransactions) in the MongoDB documentation.



## Rule 
``` MONGODB_GETPARAMETER
db.adminCommand( { setParameter: 1, "wiredTigerConcurrentWriteTransactions": "128"  } ) 
```
 
## Resolution
Follow the steps below to adjust the verbosity of your logs. This can also be done online: 
```mongo> db.adminCommand( { setParameter: 1, "wiredTigerConcurrentWriteTransactions": "128"  } )```

Set to default: Edit **mongod.conf** and set the parameter below:
``` setParameter:     wiredTigerConcurrentWriteTransactions: 128``` 

If you are resetting the write ticket in your mongod config file, the change will not take effect until the next restart.

## Need more support from Percona?
Subscribe to Percona Platform to get database support with guaranteed SLAs or proactive database management services from the Percona team.

[Learn more :fontawesome-solid-paper-plane:](https://per.co.na/subscribe){ .md-button }
