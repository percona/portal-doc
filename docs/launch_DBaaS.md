# Launch a Percona DBaaS environment

Launch a free Kubernetes cluster, automatically provisioned with a PMM server, for which the Database as a Service (DBaaS) feature is already enabled.

PMM DBaaS is an open-source solution to run and manage MySQL and MongoDB clusters on Kubernetes.

The free clusters have three worker nodes, 4 CPUs/8GB of RAM, and expire in three hours. This makes them ideal for testing out PMM with DBaaS in a native Kubernetes experience.

You can create one free cluster per day.

To launch a free cluster:

1. In the **Percona DBaaS** tab, select **Launch temporary cluster**. With that, the cluster is provisioned. Within a few minutes, it’ll be ready to use.
2. Once the cluster is created, click **Access Percona DBaaS**.
3. Go to your PMM instance and click <i class="uil uil-database"></i> **DBaaS** on the left menu.
4. Open the **Kubernetes Cluster** tab, and click **Create DB cluster** to create your MongoDB or MySQL cluster.

For more information about working with clusters in PMM, see 
