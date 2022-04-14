## MongoDB Localhost bypass check

This check returns a warning if MongoDB **enableLocalhostAuthBypass** parameter is set to True.
This represents a security vulnerability and should be disabled. For more information, see the [MongoDB documentation](https://docs.mongodb.com/manual/reference/parameters/#mongodb-parameter-param.enableLocalhostAuthBypass). 

## Rule
``` MONGODB_GETPARAMATER
db.adminCommand({'getParameter':'*'}).enableLocalhostAuthBypass
true



parsed = docs[0]["parsed"]
          print(repr(parsed))
          setParameter = parsed.get("setParameter", {})
          enableLocalhostAuthBypass = (setParameter.get("enableLocalhostAuthBypass") == "true")
```

## Resolution
Disable localhost bypass:

1. Edit **mongod.conf** and set the below parameter.
```setParameter:
  enableLocalhostAuthBypass: false
```
2. Perform a rolling restart of your mongod nodes to apply the changes. 
