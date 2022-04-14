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

|Database |MySQL Check      | Description |  Anonymous Checks | Registered  Checks   | Paid Checks    | 
| :----------| :----------- |:----------- |:----------- | :----------- | :----------- |
|MongoDB|MongoDB Active vs Available Connections|Check the ratio between Active and Available connections| <input type="checkbox" disabled  />  |<input type="checkbox" checked /> | <input type="checkbox" checked />|
||MongoDB Authentication|Warns if MongoDB authentication is disabled.| <input type="checkbox" disabled  />  |<input type="checkbox" checked /> | <input type="checkbox" checked />|
||MongoDB Security AuthMech|Warns if MongoDB is not using the default SHA-256 hashing as SCRAM authentication method.| <input type="checkbox" disabled  />  |<input type="checkbox" disabled  /> | <input type="checkbox" checked />|
||MonogDB IP bindings|Warns if MongoDB network binding is not set as recommended.| <input type="checkbox" checked  />  |<input type="checkbox" checked /> | <input type="checkbox" disabled  />|
||MongoDB CVE Version|Shows an error if MongoDB or Percona Server for MongoDB version is not the latest one with CVE fixes.| <input type="checkbox" checked  />  |<input type="checkbox" checked /> | <input type="checkbox" disabled  />|
||MongoDB Journal Check|Warns if journal is disabled.| <input type="checkbox" disabled   />  |<input type="checkbox" checked /> | <input type="checkbox" disabled  />|
||MongoDB localhost authentication bypass is enabled| Warns if MongoDB localhost bypass is enabled.| <input type="checkbox" checked  />  |<input type="checkbox" checked /> | <input type="checkbox" disabled  checked/>|
||MongoDB Non-Default Log Level|Warns if MongoDB is not using the default log level.| <input type="checkbox" disabled   />  |<input type="checkbox" disabled  /> | <input type="checkbox" checked />|
||MongoDB Profiling Level|Warns when the MongoDB profile level is set to collect data for all operations.| <input type="checkbox" disabled   />  |<input type="checkbox" checked /> | <input type="checkbox" checked />|
||MongoDB Read Tickets|Warns if MongoDB is using more than 128 read tickets.| <input type="checkbox" disabled   />  |<input type="checkbox" disabled  /> | <input type="checkbox" checked />|
||MongoDB Replica Set Topology	|Warns if the Replica Set cluster has less than three members.| <input type="checkbox" disabled   />  |<input type="checkbox" checked /> | <input type="checkbox" checked />|
||MongoDB Version	|Warns if MongoDB or Percona Server for MongoDB version is not the latest one.| <input type="checkbox" checked  />  |<input type="checkbox" checked /> | <input type="checkbox" checked />|
||MongoDB write Tickets	|Warns if MongoDB network is using more than 128 write tickets.| <input type="checkbox" disabled   />  |<input type="checkbox" disabled  /> | <input type="checkbox" checked />|
|MySQL|Check if binaries are 32-bits	|Notifies if version_compatible_machine equals i686.| <input type="checkbox" disabled   />  |<input type="checkbox" checked  /> | <input type="checkbox" checked />|
||Automatic User Expired Password	|Notifies if version_compatible_machine equals i686.| <input type="checkbox" disabled   />  |<input type="checkbox" checked  /> | <input type="checkbox" checked />|
||InnoDB flush method and File Format check	|Checks the following settings: **innodb_file_format**, **innodb_file_format_max**, **innodb_flush_method** and **innodb_data_file_path**.| <input type="checkbox" disabled   />  |<input type="checkbox" checked  /> | <input type="checkbox" checked />|
||Checks based on values of MySQL configuration variables	|| <input type="checkbox" disabled   />  |<input type="checkbox"  disabled /> | <input type="checkbox" checked />|
||Binary Logs checks, Local infile and SQL Mode checks	|Warns about non-optimal settings for Binary Log, Local Infile and SQL mode.| <input type="checkbox" disabled   />  |<input type="checkbox"  checked/> | <input type="checkbox" checked />|
|| Configuration check	|| <input type="checkbox" disabled   />  |<input type="checkbox"  disabled /> | <input type="checkbox" checked />|
|| Users With Granted Public Networks Access	|| <input type="checkbox" disabled   />  |<input type="checkbox"  checked/> | <input type="checkbox" checked />|
|| User check	|Runs a check on user setup| <input type="checkbox" disabled   />  |<input type="checkbox"  checked/> | <input type="checkbox" checked />|
|| User check	|Runs a high-level check on user setup| <input type="checkbox" disabled   />  |<input type="checkbox"  checked/> | <input type="checkbox" checked />|
|| Advanced User check	|Runs a detailed check on user setup| <input type="checkbox" disabled   />  |<input type="checkbox"  disabled /> | <input type="checkbox" checked />|
|| Security check	|Runs a detailed check on user setup| <input type="checkbox" disabled   />  |<input type="checkbox"  disabled /> | <input type="checkbox" checked />|
||Test Database|| <input type="checkbox" disabled   />  |<input type="checkbox"  checked /> | <input type="checkbox" checked />|
||MySQL Version|Warns if MySQL, Percona Server for MySQL, or MariaDB version is not the latest one.| <input type="checkbox" checked  />  |<input type="checkbox"  checked /> | <input type="checkbox" checked />|
|PostgreSQL| Archiver is failing| Verifies if the archiver has failed.|<input type="checkbox" disabled   />  |<input type="checkbox"  disabled  /> | <input type="checkbox" checked />|
|| Cache hit ratio| Checks database hit ratio and complains when this is too low.|<input type="checkbox" disabled   />  |<input type="checkbox"  disabled  /> | <input type="checkbox" checked />|
|| Cache hit ratio| Checks database hit ratio and complains when this is too low.|<input type="checkbox" disabled   />  |<input type="checkbox"  disabled  /> | <input type="checkbox" checked />|
|| Cache hit ratio| Checks database hit ratio and complains when this is too low.|<input type="checkbox" disabled   />  |<input type="checkbox"  disabled  /> | <input type="checkbox" checked />|
|| Configuration change requires restart/reload.| Warns when a configuration was changed and requires a server restart/reload|<input type="checkbox" disabled   />  |<input type="checkbox"  checked  /> | <input type="checkbox" checked />|
|| PostgreSQL fsync is disabled| Shows an error if the fsync configuration is disabled, as this can result in unrecoverable data corruption.|<input type="checkbox" checked   />  |<input type="checkbox"  checked  /> | <input type="checkbox" checked />|
|| PostgreSQL Autovacuum Logging Is Disabled| Shows an error if the fsync configuration is disabled, as this can result in unrecoverable data corruption.|<input type="checkbox" disabled   />  |<input type="checkbox"  disabled  /> | <input type="checkbox" checked />|
|| Autovacuum Logging Is Disabled|Notifies if the log_autovacuum_min_duration configuration option is set to -1 (disabled ).|<input type="checkbox" disabled   />  |<input type="checkbox"  disabled  /> | <input type="checkbox" checked />|
|| Checkpoints Logging Is Disabled|Notifies if the **log_checkpoints **configuration option is not enabled.|<input type="checkbox" disabled   />  |<input type="checkbox"  checked  /> | <input type="checkbox" checked />|
|| Max_connections is too high.|Notifies if the max_connections setting is set above 300.|<input type="checkbox" checked   />  |<input type="checkbox"  checked  /> | <input type="checkbox" checked />|
|| Stale Replication Slot|Notifies if the max_connections setting is set above 300.|<input type="checkbox" disabled   />  |<input type="checkbox"  disabled  /> | <input type="checkbox" checked />|
|| Super Role	|Notifies if there are users with superuser privileges.|<input type="checkbox" checked   />  |<input type="checkbox"  checked  /> | <input type="checkbox" checked />|
|| Version Check| Warns if the PostgreSQL minor or major versions are not the latest, and shows an error if the major version is 9.4 or older.|<input type="checkbox" checked   />  |<input type="checkbox"  checked  /> | <input type="checkbox" checked />|
|| MongoDB down| |<input type="checkbox" checked   />  |<input type="checkbox"  checked  /> | <input type="checkbox" checked />| 