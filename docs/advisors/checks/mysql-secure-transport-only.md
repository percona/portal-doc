# MySQL secure transport only

## Description

Checks if connections from a client are required to use secure transport. Enabling `require_secure_transport` allows only TCP/IP connections that are encrypted by TLS/SSL, or a socket in Liunx. Non-secure connections are rejected.

For more information: [Using encrypted connections](https://dev.mysql.com/doc/mysql-security-excerpt/8.0/en/using-encrypted-connections.html)


## Rule

```
           for row in docs[0]:
               name, value = row["Variable_name"], row["Value"]
               if name == "require_secure_transport":
                if value == "OFF":
```

## Resolution

Consider enabling secure transport.

## Need more support from Percona?

Subscribe to Percona Platform to get database support with guaranteed SLAs or proactive database management services from the Percona team.

[Learn more :fontawesome-solid-paper-plane:](https://per.co.na/subscribe){ .md-button }
