# MongoDB - Multiple mongod service running in a single node

## Description
This check returns warns if multiple mongod services are running on a single node.

## Resolution

Running multiple mongod services on a single instance can be useful in certain scenarios, such as when you need to isolate different workloads or databases on the same hardware. However, it's important to consider potential downsides before deciding to run multiple mongod services on a single instance.

Here are some of the potential downsides of running multiple mongod services on a single instance:

- **Resource contention:** Running multiple mongod services on the same hardware can result in resource contention, such as CPU usage, memory usage, and disk I/O. This can impact the performance and stability of all mongod instances on the same instance.
  - One important point is to configure the wiredTiger Cache Size, since by default each mongod service takes ~50% of the RAM. If other applications and services running on the server might not have enough memory to perform.
  - It's important to leave enough memory for the operating system and other applications to ensure stable performance.
  - It's important to note that the WiredTiger cache size should not exceed the available memory on the server, as this can lead to excessive swapping and poor performance.

- **Security risks:** Running multiple mongod services on the same instance can increase the security risks, as a compromise of one instance can potentially impact other instances on the same instance.

- **Increased complexity:** Running multiple mongod services on the same instance adds complexity to the deployment, as you need to manage multiple instances and their configuration files. This can make it more difficult to troubleshoot issues and perform maintenance tasks.

**Recommendations:**
Below are the recommendations for good stability and performance of a mongod instance -
1. Run a single mongod service per node.
2. For some reason if you want to run multiple mongod instances, then it is better to use containers/virtual machines which isolate different workloads or databases on the same node.



## Need more support from Percona?
Subscribe to Percona Platform to get database support with guaranteed SLAs or proactive database management services from the Percona team.

[Learn more :fontawesome-solid-paper-plane:](https://per.co.na/subscribe){ .md-button }
