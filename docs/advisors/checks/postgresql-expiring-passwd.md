# PostgreSQL roles with expiring passwords

## Description

This advisor checks roles that have expiration dates on passwords. This is helpful in preventing applications accounts from failing due to expired passwords thus preventing interruptions to services offered.

If a password expires in 10 days or less,  an Error flag is raised. If the password expires in more than 10 days, a Warning flag is raised. 


## Resolution

Consider extending the password expiration for the role in question if your policy allows for it.
You can extend a password expiration with the following syntax:

```ALTER ROLE foo WITH VALID UNTIL '2023-12-25 00:00:00';```

or

```ALTER ROLE foo WITH PASSWORD ‘foobar’ VALID UNTIL '2023-12-25 00:00:00';```

## Need more support from Percona?

Subscribe to Percona Platform to get database support with guaranteed SLAs or proactive database management services from the Percona team.

[Learn more :fontawesome-solid-paper-plane:](https://per.co.na/subscribe){ .md-button }
