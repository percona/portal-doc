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
