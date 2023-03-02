# MySQL InnoDB password lifetime

## Description
Passwords are set to never expire if the default password expiry time is set to **0**.
This makes passwords more vulnerable to force attacks, and increases the likelihood of the password being leaked somewhere else and being used to attack the database.



## Rule
```
        SELECT @@global.default_password_lifetime;
```

## Resolution
This setting (default_password_lifetime) is set to 360 (days) by default, and we strongly recommend leaving it set to a positive integer to force users to periodically change their password..  This is an on-line change that can be applied with:

`SET GLOBAL default_password_lifetime=120;`


## Need more support from Percona?
Subscribe to Percona Platform to get database support with guaranteed SLAs or proactive database management services from the Percona team.

[Learn more :fontawesome-solid-paper-plane:](https://per.co.na/subscribe){ .md-button }
