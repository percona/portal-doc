# User not using SSL protocol to connect

## Description
When MySQL server is configured with SSL, users can still connect to the server using `--ssl-mode=disabled`. 

In this case, the connection will not be encrypted and data will be subject to sniffing. 

When using SSL, it is recommended to enforce it for all users. 

## Resolution
To prevent users from connecting using an insecure protocol, you can act at instance-level:
```
[mysqld]
require_secure_transport=ON
```
Or when creating the user:
`CREATE USER 'jeffrey'@'localhost' REQUIRE SSL;`
 
#### Need help with this?

[Ask a Percona Expert :fontawesome-solid-paper-plane:](https://www.percona.com/about-percona/contact){ .md-button }