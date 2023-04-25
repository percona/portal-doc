# Launch a Percona Monitoring and Management (PMM) environment

Test-drive PMM from within Percona Platform by generating a free Kubernetes cluster, automatically provisioned with a PMM server, for which the PMM Database as a Service (DBaaS) feature is already enabled.
This is an open-source solution to run and manage MySQL and MongoDB clusters on Kubernetes.

The free clusters have three worker nodes, 4 CPUs/8GB of RAM, and expire in three hours. This makes them ideal for testing out PMM with DBaaS in a native Kubernetes experience.

You can create one free cluster per day.

To launch a free PMM environment:

1. In the **Percona Monitoring and Management (PMM)** tab, select **Launch PMM environment**. With that, the cluster is provisioned. Within a few minutes, it’ll be ready to use.
2. Once the cluster is created, click **Access PMM environment**.
3. Go to your PMM instance and click <i class="uil uil-database"></i> **DBaaS** on the left menu.
4. Open the **Kubernetes Cluster** tab. This shows your new Kubernetes cluster as **Active**.
5. Click **Create DB cluster** to create the cluster for PMM monitoring.
6. Choose whether you want to create a MySQL or MongoDB database.
7. 





For more information about working with clusters in PMM, see 



Your database will be ready in a few minutes, you will get the endpoint to connect to and the username and password. By default the database is not exposed publicly and reachable only within the Kubernetes cluster. You can change it in the Advanced Options when creating the database.