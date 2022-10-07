# Check mongodb localhost bypass

## Description
This check returns a warning if MongoDB enableLocalhostAuthBypass parameter is set to true.

This represents a security vulnerability and should be disabled

Check docs for [more information](https://docs.mongodb.com/manual/reference/parameters/#mongodb-parameter-param.enableLocalhostAuthBypass)


## Rule
```
MONGODB_GETPARAMATER
db.adminCommand({'getParameter':'*'}).enableLocalhostAuthBypass
true

            enableLocalhostAuthBypass = docs[0]["enableLocalhostAuthBypass"]
            print(repr(enableLocalhostAuthBypass))
            if enableLocalhostAuthBypass == "true":
```


## Resolution
Please Perform the steps mentioned below to disable localhost bypass:
1. Edit mongod.conf and set the below parameter.
```
setParameter:
  enableLocalhostAuthBypass: false
```

2. Perform a rolling restart of your mongod nodes to make the changes into effect
   
