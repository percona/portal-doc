# MongoDB journal enabled

## Description
This advisor warns if the journal is not enabled. 
This is dangerous because you could have a serious issue for data durability in case of a failure.

For Production systems, enable journal to ensure that data files are valid/recoverable.

It is always recommended to enable the journal. 

More recent versions of MongoDB don’t allow turning off the journal. 
MongoDB enables journaling by default in recent versions (4.0 +).

For more information, see the [Journaling section in the MongoDB documentation](https://docs.mongodb.com/manual/core/journaling/).



## Rule
```
 storage_journal = parsed.get("storage.journal", {})
 journal_enabled = (storage_journal.get("enabled") == "true")
```


## Resolution

Follow the steps below to enable journaling: 

1. Enable journal. 
2. Edit **mongod.conf** and set the following parameter:
```
storage:
  journal:
	enabled: true
```
3. Roll-restart of your mongod (data bearing) nodes.

#### Need help with this?
[Ask a Percona Expert :fontawesome-solid-paper-plane:](https://www.percona.com/about-percona/contact?utm_source=pmm&utm_medium=banner&utm_campaign=advisors_readmore){ .md-button }

