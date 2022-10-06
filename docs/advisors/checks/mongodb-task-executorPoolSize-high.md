# Check taskExecutorPoolsize value

## Description
This advisor warns if the number of Task Executor connection pools (**taskExecutorPool** value set is higher than the number of available CPU cores of a server. 

This check is relevant because the performance can drop if the number of task executor pools set is too high.

The parameter also needs to be set in the configuration file, OR using **setParameter** for a runtime. 

Keep in mind that if set at runtime, the parameter setting will not persist after a restart, unless it is also in the mongodb  config file. 

To avoid performance issues, check and set the right value for your environment based on [MongoDB documentation](https://www.mongodb.com/docs/manual/reference/parameters/#mongodb-parameter-param.taskExecutorPoolSize).   

## Rule
``` yaml MONGODB_GETPARAMETER
# to fetch the value
db.adminCommand( { ‘getParameter’: ‘*’  } ).taskExecutorPoolSize

METRICS_INSTANT
# to fetch the value
mongodb_sys_cpu_num_cpus{service_name="{{.ServiceName}}"}

``` 

## Resolution
Adjust the value of this metric to match what is available on the host, or consider an upgrade to add more cores if your application needs exceed the currently allocated resources.

These settings apply only to your mongos nodes.



