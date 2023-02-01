# MySQL secure transport only

## Description
Checks if secure transport is required. More information: https://dev.mysql.com/doc/mysql-security-excerpt/8.0/en/using-encrypted-connections.html


## Rule
```
           for row in docs[0]:
               name, value = row["Variable_name"], row["Value"]
               if name == "require_secure_transport":
                if value == "OFF":
```

## Resolution
Please consider enabling secure transport.

## Need more support from Percona?
Subscribe to Percona Platform to get database support with guaranteed SLAs or proactive database management services from the Percona team.

[Learn more :fontawesome-solid-paper-plane:](https://per.co.na/subscribe){ .md-button }
