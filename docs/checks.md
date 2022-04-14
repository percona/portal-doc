Percona Monitoring and Management (PMM) includes a set of Advisors that run checks against the databases connected to PMM. The checks identify and alert you of potential security threats, performance degradation, data loss,  data corruption, non-compliance issues, etc. 

## Prerequisites for accessing Advisor checks

All checks are hosted on Percona Platform. PMM Server automatically downloads them from here when the **Advisors** and **Telemetry** options are enabled in PMM under **Configuration > Settings > Advanced Settings**. By default the **Advisors** options is disabled.

## Advisor check tiers and entitlements
Depending on the entitlements available for your Percona Account, the set of advisor checks that PMM can download from Percona Platform differ in terms of complexity and functionality. 

If your PMM instance is not connected to Percona Platform, PMM can only download the basic set of Anonymous advisor checks. 
As soon as you connect your PMM instance to Percona Platform, has access to additional checks, available only for Registered PMM instances. 

If you are a Percona customer with a Percona Customer Portal account, you also get access to Paid checks, which offer more advanced database health information.
​
## Checks results

The checks can be executed manually or automatically. By default, PMM runs automatic checks every 24 hours. 

You can configure this interval in **PMM > Advanced Settings > Execution intervals**. Here you can label each check individually as **Standard**, **Rare** or **Frequent** and also specify the time interval for each category.

The results are sent to PMM Server where you can review any failed checks on the **Home Dashboard > Failed Advisor Checks** panel. The summary count of failed checks is classified as <b style="color:#e02f44;">Critical</b>, <b style="color:#e36526;">Major</b> and <b style="color:#5794f2;">Trivial</b>:

![!Failed Advisor Checks panel](_images/PMM_Home_Dashboard_Panels_Failed_Advisors.jpg)

Check results data always remains on the PMM Server and are not related to anonymous data sent for Telemetry purposes.

For information on configuring PMM Advisors, see the [Percona Monitoring and Management documentation](https://www.percona.com/doc/percona-monitoring-and-management/2.x/how-to/advisors.html).

## List of checks 

Percona Platform hosts all Advisor checks available for MySQL, MongoDB and PostgreSQL databases connected to PMM. Check the full list of checks and their availability to **anonymous**, **registered** and **paid** PMM instances in the table below: 

|Database |MySQL Check      | Description |  Anonymous (PMM not connected to Percona Platform) | Registered (Connected PMM instances)| Paid (PMM instances connected with a Customer account)| 
| :----------| :----------- |:----------- |:----------- | :----------- | :----------- |
|MongoDB|MongoDB Active vs Available Connections|Check the ratio between Active and Available connections| <input type="checkbox" disabled  />  |<input type="checkbox" disabled checked /> | <input type="checkbox" disabled checked />|
||MongoDB Authentication|Warns if MongoDB authentication is disabled.| <input type="checkbox" disabled  checked/>  |<input type="checkbox" disabled checked /> | <input type="checkbox" disabled checked />|
||MongoDB Security AuthMech|Warns if MongoDB is not using the default SHA-256 hashing as SCRAM authentication method.| <input type="checkbox" disabled  />  |<input type="checkbox" disabled  /> | <input type="checkbox" disabled checked />|
||MonogDB IP bindings|Warns if MongoDB network binding is not set as recommended.| <input type="checkbox" disabled checked  />  |<input type="checkbox" disabled checked /> | <input type="checkbox" disabled  />|
||MongoDB CVE Version|Shows an error if MongoDB or Percona Server for MongoDB version is not the latest one with CVE fixes.| <input type="checkbox" disabled checked  />  |<input type="checkbox" disabled checked /> | <input type="checkbox" disabled  />|
||MongoDB Journal Check|Warns if journal is disabled.| <input type="checkbox" disabled   />  |<input type="checkbox" disabled checked /> | <input type="checkbox" disabled  />|
||MongoDB localhost authentication bypass is enabled| Warns if MongoDB localhost bypass is enabled.| <input type="checkbox" disabled checked  />  |<input type="checkbox" disabled checked /> | <input type="checkbox" disabled  checked/>|
||MongoDB Non-Default Log Level|Warns if MongoDB is not using the default log level.| <input type="checkbox" disabled   />  |<input type="checkbox" disabled  /> | <input type="checkbox" disabled checked />|
||MongoDB Profiling Level|Warns when the MongoDB profile level is set to collect data for all operations.| <input type="checkbox" disabled   />  |<input type="checkbox" disabled checked /> | <input type="checkbox" disabled checked />|
||MongoDB Read Tickets|Warns if MongoDB is using more than 128 read tickets.| <input type="checkbox" disabled   />  |<input type="checkbox" disabled  /> | <input type="checkbox" disabled checked />|
||MongoDB Replica Set Topology	|Warns if the Replica Set cluster has less than three members.| <input type="checkbox" disabled   />  |<input type="checkbox" disabled checked /> | <input type="checkbox" disabled checked />|
||MongoDB Version	|Warns if MongoDB or Percona Server for MongoDB version is not the latest one.| <input type="checkbox" disabled checked  />  |<input type="checkbox" disabled checked /> | <input type="checkbox" disabled checked />|
||MongoDB write Tickets	|Warns if MongoDB network is using more than 128 write tickets.| <input type="checkbox" disabled   />  |<input type="checkbox" disabled  /> | <input type="checkbox" disabled checked />|
|MySQL|Check if binaries are 32-bits	|Notifies if version_compatible_machine equals i686.| <input type="checkbox" disabled   />  |<input type="checkbox" checked  /> | <input type="checkbox" disabled checked />|
||Automatic User Expired Password	|Notifies if version_compatible_machine equals i686.| <input type="checkbox" disabled   />  |<input type="checkbox" checked  /> | <input type="checkbox" disabled checked />|
||InnoDB flush method and File Format check	|Checks the following settings: **innodb_file_format**, **innodb_file_format_max**, **innodb_flush_method** and **innodb_data_file_path**.| <input type="checkbox" disabled   />  |<input type="checkbox" checked  /> | <input type="checkbox" disabled checked />|
||Checks based on values of MySQL configuration variables	|| <input type="checkbox" disabled   />  |<input type="checkbox"  disabled /> | <input type="checkbox" disabled checked />|
||Binary Logs checks, Local infile and SQL Mode checks	|Warns about non-optimal settings for Binary Log, Local Infile and SQL mode.| <input type="checkbox" disabled   />  |<input type="checkbox"  disabled checked/> | <input type="checkbox" disabled checked />|
|| Configuration check	|| <input type="checkbox" disabled   />  |<input type="checkbox"  disabled /> | <input type="checkbox" disabled checked />|
|| Users With Granted Public Networks Access	|| <input type="checkbox" disabled   />  |<input type="checkbox"  disabled checked/> | <input type="checkbox" disabled checked />|
|| User check	|Runs a check on user setup| <input type="checkbox" disabled   />  |<input type="checkbox"  disabled checked/> | <input type="checkbox" disabled checked />|
|| User check	|Runs a high-level check on user setup| <input type="checkbox" disabled   />  |<input type="checkbox"  disabled checked/> | <input type="checkbox" disabled checked />|
|| Advanced User check	|Runs a detailed check on user setup| <input type="checkbox" disabled   />  |<input type="checkbox"  disabled /> | <input type="checkbox" disabled checked />|
|| Security check	|Runs a detailed check on user setup| <input type="checkbox" disabled   />  |<input type="checkbox"  disabled /> | <input type="checkbox" disabled checked />|
||Test Database|| <input type="checkbox" disabled   />  |<input type="checkbox"  disabled checked /> | <input type="checkbox" disabled checked />|
||MySQL Version|Warns if MySQL, Percona Server for MySQL, or MariaDB version is not the latest one.| <input type="checkbox" disabled checked  />  |<input type="checkbox"  disabled checked /> | <input type="checkbox" disabled checked />|
|PostgreSQL| Archiver is failing| Verifies if the archiver has failed.|<input type="checkbox" disabled   />  |<input type="checkbox"  disabled  /> | <input type="checkbox" disabled checked />|
|| Cache hit ratio| Checks database hit ratio and complains when this is too low.|<input type="checkbox" disabled   />  |<input type="checkbox"  disabled  /> | <input type="checkbox" disabled checked />|
|| Cache hit ratio| Checks database hit ratio and complains when this is too low.|<input type="checkbox" disabled   />  |<input type="checkbox"  disabled  /> | <input type="checkbox" disabled checked />|
|| Cache hit ratio| Checks database hit ratio and complains when this is too low.|<input type="checkbox" disabled   />  |<input type="checkbox"  disabled  /> | <input type="checkbox" disabled checked />|
|| Cache hit ratio| Checks database hit ratio and complains when this is too low.|<input type="checkbox" disabled   />  |<input type="checkbox"  disabled  /> | <input type="checkbox" disabled checked />|



















|Database |MySQL Check      | Description |  Anonymous (PMM not connected to Percona Platform) | Registered (Connected PMM instances)| Paid (PMM instances connected with a Customer account)| 
| :----------| :----------- |:----------- |:----------- | :----------- | :----------- |
|MySQL|[Check if binaries are 32-bit](https://docs.percona.com/percona-platform/advisors/checks/platform-mysql-binaries-32-bit.html?h=mys#mysql-binaries-are-32-bits)| Alert if binaries are compiled in 32 bits. | <input type="checkbox" disabled checked />  |<input type="checkbox" disabled checked /> | <input type="checkbox" disabled checked />|
||[Users without passwords](https://docs.percona.com/percona-platform/advisors/checks/security-user-without-password.html?h=users#there-are-users-without-passwords)|Identify users that have as authentication_string an empty string char ‘’  | <input type="checkbox" disabled /> |<input type="checkbox" disabled /> | <input type="checkbox" disabled checked />|
||[Anonymous users](https://docs.percona.com/percona-platform/advisors/checks/security-anonymous-user.html?h=anony#anonymous-users)| Identify any anonymous user. | <input type="checkbox" disabled />  |<input type="checkbox" disabled /> | <input type="checkbox" disabled checked />|
||[User with open to the word scope](https://docs.percona.com/percona-platform/advisors/checks/security-user-with-open-to-the-word-scope.html?h=ope#user-with-open-to-the-word-scope)| Identify users that have as host a wild char ‘%’ |  <input type="checkbox" disabled />    | <input type="checkbox" disabled />   | <input type="checkbox" disabled checked />|
||[Non-root accounts with SUPER privileges](https://docs.percona.com/percona-platform/advisors/checks/security-anonymous-user.html?h=anony#anonymous-users)| Identify non root users that have SUPER privileges | <input type="checkbox" disabled />     |<input type="checkbox" disabled />    | <input type="checkbox" disabled checked />|
||[User not using SSL protocol to connect](https://docs.percona.com/percona-platform/advisors/checks/security-user-not-using-ssl-protocol.html?h=ssl#user-not-using-ssl-protocol-to-connect)| Identify users that are connecting using insecure protocol  |<input type="checkbox" disabled />|<input type="checkbox" disabled /> | <input type="checkbox" disabled checked />|
||[Root account can log in remotely](https://docs.percona.com/percona-platform/advisors/checks/root-account-can-login-remotely.html?h=root#root-account-can-log-in-remotely)| Identifies root account with privileges to connect from a remote platform. | <input type="checkbox" disabled />  |<input type="checkbox" disabled /> | <input type="checkbox" disabled checked />|
||[Binary logs not synced at each write]| Identifies if sync_binlog is not set to 1. | <input type="checkbox" disabled />  |<input type="checkbox" disabled />| <input type="checkbox" disabled checked />|
||[Redo log (binary log) not enabled](https://docs.percona.com/percona-platform/advisors/checks/configuration-check-log-bin.html?h=redo#mysql-redo-log-binary-log-not-enabled)| Warns if binary logging is not enabled. | <input type="checkbox" disabled />  |<input type="checkbox" disabled />| <input type="checkbox" disabled checked />|
||[General log is active](https://docs.percona.com/percona-platform/advisors/checks/configuration-check-general-log.html?h=gene#mysql-general-log-is-active)| Warns if the general log is  enabled.  | <input type="checkbox" disabled />  |<input type="checkbox" disabled />| <input type="checkbox" disabled checked />|
||[Temporary tables dimension is capped by max_heap_table_size](https://docs.percona.com/percona-platform/advisors/checks/configuration-check-tmp-table-size-limit.html?h=tempo#mysql-temporary-tables-dimension-is-capped-by-max_heap_table_size)|Alert if the max_heap_table_size and the tmp_table_size are set to different values. | <input type="checkbox" disabled />  |<input type="checkbox" disabled />| <input type="checkbox" disabled checked />|
||[Server enforced data integrity checking is disabled ](https://docs.percona.com/percona-platform/advisors/checks/configuration-check-sql-mode.html?h=traditio)| Make sure sql_node contains TRADITIONAL, STRICT_ALL_TABLES, STRICT_TRANS_TABLES | <input type="checkbox" disabled checked />  |<input type="checkbox" disabled checked /> | <input type="checkbox" disabled checked />|
||[Replica node is not configured as READ-ONLY](https://docs.percona.com/percona-platform/advisors/checks/configuration-check-replica-not-read-only.html?h=performance_schema.replication)|  checks if replication is configured and the read_only flag is set to 0.  | <input type="checkbox" disabled />  |<input type="checkbox" disabled />| <input type="checkbox" disabled checked />|
||[Replica not verifying checksums]| Warns if slave_sql_verify checksum is not set to 1.  | <input type="checkbox" disabled />  |<input type="checkbox" disabled />| <input type="checkbox" disabled checked />||
 ||[Relay log on the replica node, not automatically purged](https://docs.percona.com/percona-platform/advisors/checks/configuration-check-relay-log-purge.html?h=purged)| Warns if the relay_log_purge variable is not set to 1. |<input type="checkbox" disabled />  |<input type="checkbox" disabled />| <input type="checkbox" disabled checked />|
||[Binary log checksums disabled]|Checks if checksumming is enabled for binary logs| <input type="checkbox" disabled />  |<input type="checkbox" disabled checked /> | <input type="checkbox" disabled checked />|
||[Binary Log Row-based images excessive]|This advisor checks if ROW images stored on binlogs are optimized to save disk space or not | <input type="checkbox" disabled />  |<input type="checkbox" disabled checked /> | <input type="checkbox" disabled checked />|
||[Binary logs automatically removed too quickly]|Checks if binary logs rotation period is too short |   <input type="checkbox" disabled />  |<input type="checkbox" disabled checked /> | <input type="checkbox" disabled checked />||
||[Local option of load data enabled]|  Verifies if the local infile global variable is disabled. | <input type="checkbox" disabled />  |<input type="checkbox" disabled checked /> | <input type="checkbox" disabled checked />||
||[Master not verifying checksums]| Checksum in the binary log should be enabled as a safety measure. | <input type="checkbox" disabled />  |<input type="checkbox" disabled checked /> | <input type="checkbox" disabled checked />|
||[Server enforced data integrity checking not strict]| Checks if sql_mode is not enforcing strict mode.| <input type="checkbox" disabled  />  |<input type="checkbox" disabled checked /> | <input type="checkbox" disabled checked />|
||[Sql processing not multi threaded]|Checks if replica SQL processing  is not multi-threaded | <input type="checkbox" disabled checked />  |<input type="checkbox" disabled checked /> | <input type="checkbox" disabled checked />|
||[Innodb flush method may not be optimal]| Checks if innodb_flush_method is O_DIRECT.| <input type="checkbox" disabled />  |<input type="checkbox" disabled  /> | <input type="checkbox" disabled checked />|
||[Innodb file format]| Checks if innodb_file_format is Barracuda.| <input type="checkbox" disabled />  |<input type="checkbox" disabled  /> | <input type="checkbox" disabled checked />|
||[Innodb data file path]|Checks if there is any size limitation for tablespaces.| <input type="checkbox" disabled />  |<input type="checkbox" disabled  /> | <input type="checkbox" disabled checked />|
||[Replica without replication slave account]| Checks if a user with the Replication grants exists.| <input type="checkbox" disabled />  |<input type="checkbox" disabled checked /> | <input type="checkbox" disabled checked />|

