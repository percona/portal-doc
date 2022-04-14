# MongoDB Active vs Available connections

## Description
This check returns a warning if the ratio of Active versus Available connections is higher than 75%. 

This check is relevant because the risk is running out of connections. If this happens application wonìt ba able to connect to MongoDB.

## Resolution
It is recommended to increase the ULIMIT to permit more connections or the current workload from applications to be evaluated.

An unexpected spike on the workload or not optimized queries could be the root cause of more active connections.
