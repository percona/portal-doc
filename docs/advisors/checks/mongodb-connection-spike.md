# MongoDB Connections sudden spike

## Description
This check returns a warning if there is an increase in the number of connections that is higher than 50% of the most recent or normal number of connections.

## Resolution

A sudden spike in MongoDB connections can be caused by multiple factors, including:

1. **Increased User Traffic:** If there has been a sudden increase in the number of users accessing your MongoDB database, it could result in a spike in connections.

2. **Database Maintenance:** If database maintenance activities such as backups, indexing, or data migrations are being performed, it could result in a spike in connections when a restart occurs or when application servers reconnect.

3. **Poor Connection Pooling:** If your application is not using connection pooling properly, it could result in a spike in connections as new connections are created and old ones are not properly closed.

4. **New batch jobs:** If there are new batch jobs added it can cause a spike in the number of connections.

5. **Long-running Queries:** Long-running queries can also result in a spike in connections as they tie up resources, preventing new connections from being established. This could cause connections to queue.

6. **Poorly Configured Connection Limits:** If your MongoDB database is not configured with appropriate connection limits, it could result in a spike in the number of connections as new connections are created.

7. **Security Attacks:** Malicious actors can sometimes launch attacks to create a sudden surge of connections in an attempt to overwhelm and disrupt the database. An example of this would be Denial of Service (DOS) attacks. 


To diagnose the root cause of the sudden spike in connections, you should examine your logs and check related performance metrics to identify any unusual patterns or activity. This can help you determine if the issue is related to user traffic, application code, database configuration, or security issues.

Some of the key Performance metrics that need to be examined are:
- Number of connections
- Query executors & Query targeting
- Opcounters
- Queues
- Locks time and count
- Operation execution time
- Replication lag
- MongoS logs in sharded clusters
- OS and system logs
- Network related logs
- System and Resource Utilization
  - CPU 
  - Memory
  - Disk - Disk latency, Disk IOPS




## Need more support from Percona?
Subscribe to Percona Platform to get database support with guaranteed SLAs or proactive database management services from the Percona team.

[Learn more :fontawesome-solid-paper-plane:](https://per.co.na/subscribe){ .md-button }
