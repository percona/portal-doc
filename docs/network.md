# Network configuration

Percona Platform communicates with PMM to provide the PMM instances connected to the organization with advanced advisor checks, alert rule templates, product updates and  automated insights.

If you are running PMM in a locked-down corporate environment without direct access to the Internet, PMM will not be able to establish a connection to PMM to download any of these services.

In such scenarios, configure your network firewall, so that all ports and hosts listed below are enabled for bi-directional communication. User Datagram Protocol (UDP) is not needed.

Ports to expose:


| PMM component  | IP Address      | TCP Port | Description
|----------------|-----------------|----------|-----------------------------------------------------------------------------------------------------------------
| RESERVED       | 3.135.83.118    | -        | Reserved for future needs.
| PMM snapshots  | 18.219.251.83   | 443      |  Service for sharing snapshots of PMM dashboards with Percona. (snapshots-g710.percona.com)
| PMM snapshots  | 3.140.123.9     | 443      | Service for sharing snapshots of PMM dashboards with Percona. (snapshots-g710.percona.com)
| Percona Portal | 3.22.94.230     | 443      |  Percona Portal services (check.percona.com, platform.percona.com, portal.percona.com)
| Percona Portal | 3.140.105.0     | 443      |  Percona Portal services (check.percona.com, platform.percona.com, portal.percona.com)
