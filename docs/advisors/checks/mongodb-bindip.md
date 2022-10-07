# Check mongodb bind IP

## Description
This advisor warns if the number of Task Executor connection pools (**taskExecutorPool** value set is higher than the number of available CPU cores of a server. 

This check returns a warning if MongoDB network binding setting is not recommended.

This is to avoid possible security breach from listening to unidentified client IP addresses. 

Check docs for [more information](https://docs.mongodb.com/manual/reference/configuration-options/#mongodb-setting-net.bindIp)


## Rule
```
MONGODB_GETCMDLINEOPTS
db.adminCommand({'getCmdLineOpts':1}).parsed.net.bindIp


net = parsed.get("net", {})
            bindIP = (net.get("bindIp") == "0.0.0.0")
            bindIP = bindIP or ("bindIpAll" in net)
```


## Resolution
Please Perform the steps mentioned below to adjust network binding settings

1. Adjust IP addresses in net.bindIp or bindIpAll boolean flag
Edit mongod.conf and set the below parameter.
```
net:
  bindIp: <private IP or hostname of DB server>
  #bindIpAll: false //Any of these parameters might be enabled so adjust accordingly
```
2. Perform a rolling restart of your mongod nodes to make the changes into effect
   
