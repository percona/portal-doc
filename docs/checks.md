Percona Monitoring and Management (PMM) offers four database Advisors to help you improve database performance: Configuration Advisors, Performance Advisors, Query Advisors and Security Advisors. 

Each Advisor includes a set of automated checks, which investigate a specific range of possible issues and areas of improvement: security threats, non-compliance issues, performance degradation, query and index optimization strategies etc.

All Advisors and their checks are hosted on Percona Platform. PMM Server automatically downloads them from here when the **Advisors** and **Telemetry** options are enabled in PMM under **Configuration > Settings > Advanced Settings**. Both options are enabled by default.

## Advisors plans 

### Built-in Advisors
By default, PMM comes with the basic checks included in the Configuration and the Security Advisors: **Configuration Versions** and **CVE Security**.
When your PMM instance is not connected to Percona Platform, PMM can only provide these built-in Anonymous Advisor checks.

### How to get more advisors
As soon as you connect your PMM instance to Percona Platform, PMM has access to extra advisors, available for Registered PMM instances only.

If you are a Percona customer with a Percona Customer Portal account, you get additional access to Paid checks, which offer even more advanced database health information.

Depending on the entitlements available for your Percona Account, the set of Advisor checks that PMM can download from Percona Platform differ in terms of complexity and functionality. For information about which Advisor checks are included in our subscriptions, see the [Percona Platform Subscription plans](https://www.percona.com/software/percona-platform/subscription).

## List of Advisos
Check out the complete list of checks and their availability for **Basic**, **Standard**, and **Premium** plans in the tables below:


### Configuration Advisors

| Check Name | Description | Tier | Database Technology|
| :--------- | :---------- | :--- |:--- |
| **Version Configuration** | Notifies of newly released database versions to streamline database maintenance and ensure the most up-to-date performance. | Anonymous, Registered, Paid | MySQL, MongoDB, PostgreSQL|
| **Generic Configuration** | Provides basic recommendations for improving your database configuration.   | Registered, Paid |MySQL, MongoDB, PostgreSQL| 
| **Resources Configuration** | Watches your database and gives you recommendations for efficient management of resources like binaries architecture, CPU number versus DB Configuration, etc. | Registered, Paid | MongoDB, PostgreSQL|
| **Connection Configuration** |Provides recommendations on configuring database connection parameters for improving database performance.  | Paid |PostgreSQL|
| **Replication Configuration** | Provides recommendations for scalable replication in database clusters. | Paid | MySQL, MongoDB|
| **InnoDB Configuration** | Advises on configuring InnoDB optimization for high performance. | Paid | MySQL, MongoDB, PostgreSQL|
| **Vacuum Configuration** | Provides recommendations on optimizing Vacuum operations. | Paid | MySQL, MongoDB, PostgreSQL|

### Performance Advisors

| Check Name | Description | Tier | Database Technology|
| :--------- | :---------- | :--- |:--- |
| **Generic Performance** | Provides basic database configuration recommendations for high-performance query execution. | Registered, Paid | PostgreSQL|
| **Vacuum Performance** | Helps improve the efficiency and execution speed of database Vacuum commands. |  Paid | MySQL, MongoDB, PostgreSQL|
| **Replication Performance** |Checks efficient replication usage of your database. | Paid |PostgreSQL|


### Security Advisors
| Check Name | Description | Tier | Database Technology|
| :--------- | :---------- | :--- |:--- |
| **CVE Security** | Informs you of any database versions affected by CVE. | Anonymous, Registered, Paid | MongoDB |
| **Configuration Security** | Checks your database configuration to ensure that security best practices are correctly implemented.  | Registered, Paid |MySQL, MongoDB|
| **Authentication Security** | Ensures that all database authentication parameters are configured securely. | Paid |MySQL, MongoDB, PostgreSQL|
| **Replication Security** | Helps safeguard data replication by assessing security risks and providing recommendations for improving protection. | Paid |MySQL|
| **Connection Security** | Helps identify security issues on network connections and provides recommendations for enhancing security. | Paid |MySQL, MongoDB|

### Query Advisors
| Check Name | Description | Tier | Database Technology|
| :--------- | :---------- | :--- |:--- |
| **Index Query** | Provides query and index optimization strategies for peak database performance. | Paid | MySQL |
| **Schema Design Query** | Helps create efficient database schemas by analyzing queries and offering suggestions for optimization. | Registered, Paid |MySQL|
