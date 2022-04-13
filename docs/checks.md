Percona Monitoring and Management (PMM) includes a set of Advisors that run checks against the databases connected to PMM. The checks identify and alert you of potential security threats, performance degradation, data loss,  data corruption, non-compliance issues, etc. 

## Prerequisites for accessing Advisor checks

All checks are hosted on Percona Platform. PMM Server automatically downloads them from here when the **Advisors** and **Telemetry** options are enabled in PMM under **Configuration > Settings > Advanced Settings**. By default the **Advisors** options is disabled.

### Advisor check tiers and entitlements
Depending on the entitlements available for your Percona Account, the set of advisor checks that PMM can download from Percona Platform differ in terms of complexity and functionality. 

If your PMM instance is not connected to Percona Platform, PMM can only download the basic set of Anonymous advisor checks. 
As soon as you connect your PMM instance to Percona Platform, has access to additional checks, available only for Registered PMM instances. 

If you are a Percona customer with a Percona Customer Portal account, you also get access to Paid checks, which offer more advanced database health information.
​
### Checks results

The checks can be executed manually or automatically. By default, PMM runs automatic checks every 24 hours. 

You can configure this interval in **PMM > Advanced Settings > Execution intervals**. Here you can label each check individually as **Standard**, **Rare** or **Frequent** and also specify the time interval for each category.

The results are sent to PMM Server where you can review any failed checks on the **Home Dashboard > Failed Advisor Checks** panel. The summary count of failed checks is classified as <b style="color:#e02f44;">Critical</b>, <b style="color:#e36526;">Major</b> and <b style="color:#5794f2;">Trivial</b>:

![!Failed Advisor Checks panel](_images/PMM_Home_Dashboard_Panels_Failed_Advisors.jpg)

Check results data always remains on the PMM Server and are not related to anonymous data sent for Telemetry purposes.

For information on configuring PMM Security Threat Tool, see the [Percona Monitoring and Management documentation](https://www.percona.com/doc/percona-monitoring-and-management/2.x/using/security-threat-tool.html).

### List of checks 

Percona Platform hosts all the security checks available for MySQL, MongoDB and PostgreSQL databases connected to PMM. Check the full list of checks and their availability to **anonymous**, **registered** and **paid** PMM instances in the table below: 

### MySQL Advisor Checks

|MySQL Check      | Type |  Description
| :----------| :----------- |:----------- |
|MySQL Binary Logs, Local Infile and SQL Mode checks|Registered | Warns about non-optimal settings for Binary Log, Local Infile and SQL mode.|
|MySQL Binary Logs, Local Infile and SQL Mode checks|anonymous, registered | Warns about non-optimal settings for Binary Log, Local Infile and SQL mode.|
|MySQL user check| anonymous|Runs a high-level check on user setup. |
|MySQL user check| registered |Runs a detailed check on user setup. |
|MySQL version | Anonymous  |Warns if MySQL, Percona Server for MySQL, or MariaDB version is not the latest one. |
|Check if binaries are 32-bit| Anonymous  |Notifies if **version_compatible_machine** equals i686.|
|InnoDB flush method and file format check| anonymous, registered  |Checks the following settings: **innodb_file_format**, **innodb_file_format_max**, **innodb_flush_method** and **innodb_data_file_path**.  |
|Replica without replication slave account| Registered  |Checks if a user with 
|Validate Password Policy| Registered | Warns if Policy-Based Password validation does not perform dictionary checks|
|Local option of load data enabled|Registered | Warns if the local infile global variable is disabled.|
|Not_verifying_checksums| Registered | Policy-Based Password Validation Does Not Perform Dictionary Checks| 
|Sql processing not multi threaded| Registered| Warns if replica SQL processing is not multi-threaded|


## MongoDB Advisor Checks

 |MongoDB Checks      | Type |  Description
| :----------| :----------- |:----------- |
|Mongo DB profiling level|Registered |Warns when the MongoDB profile level is set to collect data for all operations. Collecting information about commands running in MongoDB instances helps identify slow queries or performance tuning. However, the profile has a negative performance impact on overall database performance and on disk usage. 
|MongoDB localhost authentication bypass is enabled | Anonymous |Warns if MongoDB localhost bypass is enabled. |
|MongoDB read tickets | anonymous, registered  |Warns if MongoDB is using more than 128 read tickets. |
|MongoDB IP bindings| Anonymous  |Warns if MongoDB network binding is not set as recommended.|
|MongoDB write tickets | anonymous, registered  |Warns if MongoDB network is using more than 128 write tickets. 
|MongoDB authentication | Anonymous|Warns if MongoDB authentication is disabled. |
|MongoDB non-default Log level | anonymous, registered  |Warns if MongoDB is not using the default log level. |
|MongoDB version | Anonymous |Warns if MongoDB or Percona Server for MongoDB version is not the latest one. |
|MongoDB security AuthMech check| anonymous, registered  |Warns if MongoDB is not using the default SHA-256 hashing as SCRAM authentication method.
|MongoDB journal| anonymous, registered  |Warns if journal is disabled.|  
|Check the Replica Set Topology| Registered| Warns if the Replica Set cluster has less than 3 members.|
|Check Active and Available connections ratio| Registered| Warns if the ratio of Active vs Available connections is higher than 75%. |

#### PostgreSQL Checks
 
|PostgreSQL Check      | Type |  Description
| :----------| :----------- |:----------- |
|PostgreSQL **max_connections** is too high| Anonymous    |  Notifies if the **max_connections** setting is set above 300. PostgreSQL doesn't handle well large number of connections, even if these connections are idle. Recommended value is below 300. |
|PostgreSQL cache hit ratio| anonymous, registered   |   Checks database hit ratio and complains when this is too low.|
|PostgreSQL Archiver is failing| anonymous, registered| Verifies if the archiver has failed. |
|MongoDB CVE version | Anonymous  |Shows an error if MongoDB or Percona Server for MongoDB version is not the latest one with CVE fixes. |
|PostgreSQL checkpoints logging is disabled |anonymous, registered  |Notifies if the **log_checkpoints** configuration option is not enabled. We recommend enabling this option to get verbose logging of the checkpoint process. This provides useful information that can be used to identify and troubleshoot sub-optimal PostgreSQL database performance.|
|PostgreSQL Autovacuum logging is disabled | anonymous, registered | Notifies if the **log_autovacuum_min_duration** configuration option is set to **-1 (disabled** ). We recommend logging autovaccum run activity, since this can provide useful information with almost no drawbacks.|
|PostgreSQL super role |Anonymous  |Notifies if there are users with superuser privileges.|
|PostgreSQL Fsync is disabled| Anonymous|Shows an error if the **fsync** configuration is disabled, as this can result in unrecoverable data corruption. |
|PostgreSQL version | Anonymous  |Warns if the PostgreSQL minor or major versions are not the latest, and shows an error if the major version is 9.4 or older.  |
|PostgreSQL stale replication slot| anonymous, registered  |Warns for stale replication slots since these can lead to WAL file accumulation and DB server outage.|
|Configuration change requires restart/reload|   anonymous, registered   | Warns when a configuration was changed and requires a server restart/reload. |