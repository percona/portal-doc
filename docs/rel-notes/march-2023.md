## Better, smarter Advisors
All through March, we published a series of new checks that increase the capabilities of our Advisors and cover all supported technologies.

The new Advisors show up in PMM on the Advisors page under a new structure that groups Advisors by categories. The new structure also clearly shows which Advisors are available for your current subscription.

While we are working on making the new structure visible on Percona Platform as well, are keen to get your feedback around these changes via the Percona Platform Forum.

### Changes to Advisors available in the Basic plan
**Version Configuration Advisors**
- All technologies are updated to notify about the latest minor and major database versions available.
- Added a new MongoDB unsupported version check and End-of-Life (EOL) version.  
Upcoming EOL for MySQL version 5.7 and check for MySQL installations not up-to-date with the latest officially supported version.
- Added PostgreSQL upcoming EOL and unsupported PostgreSQL extension version check.

### Changes to Advisors available in the Basic plan only after connecting PMM to the Percona Platform

**Resources Configuration Advisor**
- Now contains MongoDB feature compatibility version check to control the availability of new features and ensure compatibility with existing applications.
- Added one more MongoDB check for data directories and recommendations on using XFS filesystem for high scalability and performance.


**Generic Configuration Advisor**

- Contains checks for PostgreSQL minimum logging features and checks for WAL files retained for recommendations on saving more disk space.
- MongoDB Storage Cache recommends updating MongoDB configuration for WiredTiger to avoid memory issues.

**Configuration Security Advisor**

- MySQL configuration check can now spot empty “secure_file_priv” parameter and provides recommendations on more secure database installations.

### Changes to Advisors available in only the Standard and Premium
**Query Index Advisor**

- Now analyzes PostgreSQL, MongoDB statistics on indexes, identifies unused or high indexes and provides best-practises and recommendations.
- The Performance check can now determine if on-disk temporary tables are causing any performance issues in your MySQL database and recommendations on optimizing performance.

**Query schema Design Advisor**
Fixed advisor issue for PostgreSQL older than version 10.

**Replication Performance**

- ow checks for MongoDB oplog size, usage, and replication lag for each node in the replica set, and gives you specific recommendations for avoiding data loss or replication issues.

**Connection Configuration**

- Now checks for MongoDB connection sudden spike, MySQL max connection usage, and overall Connection Count.
- Recommends optimizing the application configuration to ensure that the database is performing efficiently and can handle the expected workload.

**InnoDB Configuration**

- Now notifies when the redo log files are not sized correctly, either because they are too small or too large
-Includes MySQL innodb_file_per_table configuration check for improved space management or data isolation.

## Enhanced page headers
Continuing our UX general overhauling initiative that started with the Migration to Material UI library in December, we have now tweaked the page titles, to better reflect their functionality. 

## Mobile-friendly landing page
We’ve optimized the Percona Platform landing page, to make sure it adapts the content to fit different screen sizes. So whenever you need to check on your organization on the go, just visit Percona Platform from your smartphone.

## Home page tuning
To clean things up and add more white space, we’ve removed the Alerting banner and the Tickets overview widget from the Portal Home dashboard.

## Fixed issues

- Fixed timeout issue that was generating multiple pop-up error messages when returning to an expired Percona Platform user session after a longer period of inactivity.
- Some ticket statuses were not clearly visible on the light theme. This issue is now fixed. 
- To improve security, organization names no longer accept HTML special character strings.