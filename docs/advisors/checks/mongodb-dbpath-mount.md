# MongoDB DBPATH mount

## Description
This check warns if **dbpath** does not have a dedicated mount point.

## Resolution

For tuning flexibility, we recommended that MongoDB data sits on its own disk volume, preferably with its own dedicated disks/RAID array. While it may complicate backups, for the best performance you can also dedicate a separate volume for the MongoDB journal to separate its disk activity noise from the main data set. The journal does not yet have its own config/command-line setting, so you’ll need to mount a volume to the “journal” directory inside the dbPath. For example, “/var/lib/mongo/journal” would be the journal mount-path if the dbPath was set to “/var/lib/mongo”.

There are several reasons why it is recommended to use a separate mount point for the dbPath in MongoDB:

- **Performance:** Separating the data files from the system files can help improve the performance of MongoDB. This is because the data files can be placed on a dedicated disk or disk partition, which can improve read and write performance.

- **Scalability:** By separating the data files from the system files, it becomes easier to scale the database. You can add more storage as needed without having to worry about running out of space on the system disk.

- **Maintenance:** Separating the data files from the system files makes it easier to perform maintenance tasks such as backups and restores. You can back up the data files separately from the system files, which can help reduce the time it takes to perform backups and restores.

- **Security:** By separating the data files from the system files, you can improve the security of your database. For example, you can restrict access to the data files to only those users who need it, which can help prevent unauthorized access to your data. 

For more information on tuning your database, kindly see the [Production Checklist](https://www.mongodb.com/docs/manual/administration/production-checklist-operations/).


## Need more support from Percona?
Subscribe to Percona Platform to get database support with guaranteed SLAs or proactive database management services from the Percona team.

[Learn more :fontawesome-solid-paper-plane:](https://per.co.na/subscribe){ .md-button }
