
# Check maxSessions value

## Description 

This advisor warms if the number of **maxSessions** value set exceeds the default value of **1000000** while starting the database. 

This is relevant because setting the number of sessions too high can negatively impact the performance.

The parameter also needs to be set at the configuration file.

To avoid performance issues, see [The (In)famous MongoDB Message blogpost](https://www.percona.com/blog/2021/06/03/mongodb-message-cannot-add-session-into-the-cache-toomanylogicalsessions) to check & set the right value for your environment.


## Rule

``` MONGODB_GETCMDLINEOPTS
# to fetch the value
db.adminCommand( { getCmdLineOpts: 1  } )
```
 
## Resolution
Instead of increasing **maxSessions**, first reduce the setting of the **logicalSessionRefreshMillis** parameter from the default interval of 5 minutes to run every 2 minutes. 

You can tweak the time suitable for your environment by setting and checking the performance of open sessions.

Make sure to remove the idle sessions from cache to make room for the new ones and keep the number of sessions reaching its maximum setting mostly.  
 
 See [logicalSessionRefreshMillis](https://www.mongodb.com/docs/manual/reference/parameters/#mongodb-parameter-param.logicalSessionRefreshMillis) in the MongoDB documentation. 

To avoid performance issues, see [The (In)famous MongoDB Message blogpost](https://www.percona.com/blog/2021/06/03/mongodb-message-cannot-add-session-into-the-cache-toomanylogicalsessions) to check and set the right value for your environment.  This can be adjusted for your mongod and your mongos nodes.

## Need more support from Percona?
Subscribe to Percona Platform to get database support with guaranteed SLAs or proactive database management services from the Percona team.

[Learn more :fontawesome-solid-paper-plane:](https://per.co.na/subscribe){ .md-button }
