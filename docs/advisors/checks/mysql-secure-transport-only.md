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
