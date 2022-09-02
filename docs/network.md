# Network configuration

Percona Platform communicates with PMM to provide the PMM instances connected to the organization with advanced advisor checks, alert rule templates, product updates and  automated insights.

If you are running PMM in a locked-down corporate environment without direct access to the Internet, Percona Platform will not be able to establish a connection to PMM and won't be able to download these services.

In such scenarios, configure your network firewall, so that all ports and hosts listed below are enabled for bi-directional communication. UDP is not needed.

IP Address to whitelist:

| PMM component | IP Addresses      |  Description
|---------------|---------------|---------------|-----------------------------------------------------------------------------------------------------------------
| PMM Server    |   3.135.83.118          | HTTP server, used for gRPC over HTTP and web interface (**insecure**, use with caution).
| PMM Server    |  18.219.251.83         | HTTPS server, used for gRPC over HTTPS and web interface (secure, use of SSL certificates is highly encouraged).
| PMM Server    |  3.140.123.9            | HTTPS server, used for gRPC over HTTPS and web interface (secure, use of SSL certificates is highly encouraged).
| PMM Server    |  3.22.94.230            | HTTPS server, used for gRPC over HTTPS and web interface (secure, use of SSL certificates is highly encouraged).
| PMM Server    | 3.140.105.0            | HTTPS server, used for gRPC over HTTPS and web interface (secure, use of SSL certificates is highly encouraged).

