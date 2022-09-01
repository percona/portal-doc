# Network ports

Percona Platform requires configuration of network ports to accept monitoring data from PMM. 

Make sure to configure your network and firewall so that all ports listed below are whitelisted and opened for bi-directional communication. UDP is not needed.

Ports to expose:

| PMM component | TCP port      | Direction     | Description
|---------------|---------------|---------------|-----------------------------------------------------------------------------------------------------------------
| PMM Server    |   3.135.83.118          | both          | HTTP server, used for gRPC over HTTP and web interface (**insecure**, use with caution).
| PMM Server    |  18.219.251.83          | both          | HTTPS server, used for gRPC over HTTPS and web interface (secure, use of SSL certificates is highly encouraged).
| PMM Server    |  3.140.123.9            | both          | HTTPS server, used for gRPC over HTTPS and web interface (secure, use of SSL certificates is highly encouraged).
| PMM Server    |  3.22.94.230            | both          | HTTPS server, used for gRPC over HTTPS and web interface (secure, use of SSL certificates is highly encouraged).
| PMM Server    | 3.140.105.0             | both          | HTTPS server, used for gRPC over HTTPS and web interface (secure, use of SSL certificates is highly encouraged).

