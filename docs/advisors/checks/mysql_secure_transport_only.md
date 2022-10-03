# MySQL secure transport only

## Description
Checks if secure transport is required. For more information, see [Configuring MySQL to Use Encrypted Connections](https://dev.mysql.com/doc/mysql-security-excerpt/8.0/en/using-encrypted-connections.html) in the MySQL documentation. 


## Rule
```
           for row in docs[0]:
               name, value = row["Variable_name"], row["Value"]
               if name == "require_secure_transport":
                if value == "OFF":
```

## Resolution
Consider enabling secure transport.
