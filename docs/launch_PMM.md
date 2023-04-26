# Launch a Percona Monitoring and Management (PMM) environment

Test-drive PMM from within Percona Platform by generating a free Kubernetes cluster, automatically provisioned with a PMM server, where you can try QAN, DBaaS, Advisor, Alerts and all the features that PMM has to offer.

PMM is an open-source solution for running and managing MySQL and MongoDB clusters on Kubernetes. It provides the observability required to understand database health while offering actionable insights to remediate database incidents or performance issues.  

You can create one free cluster per day. The free clusters have three worker nodes, 4 CPUs/8GB of RAM, and expire in three hours. This makes them ideal for testing out PMM in a native Kubernetes experience.


To launch a free PMM environment:

1. In the **Percona Monitoring and Management (PMM)** tab, select **Launch PMM environment**. With that, the cluster is provisioned. Within a few minutes, it’ll be ready to use.
2. Once the cluster is created, click **Access PMM environment**.
3. Go to your PMM instance and click <i class="uil uil-database"></i> **DBaaS** on the left menu.
4. Open the **Kubernetes Cluster** tab. This shows your new Kubernetes cluster as **Active**.
5. Click **Create DB cluster** to create the cluster for PMM monitoring.
6. Choose whether you want to create a MySQL or MongoDB database.
7. Verify the values in  the **Advanced Settings** and MySQL Configurations panels.
8. In the **Network and Security** panel, make sure that you enable **Expose** to make this DB cluster available outside of the Kubernetes cluster. If you want the cluster to be accessible on the Internet, also enable the **Internet Facing** option.
9. Click **Create Cluster** to create your cluster. Theis displays the **DB Cluster tab** with details about your new cluster. 
10. In the **Name** column, click on the bars icon <i class="uil uil-graph-bar"> next to the cluster name to open the Custer Summary Dashboard where you can start monitoring your database server using the available PMM metrics.
11. Use the menu on the left side to explore other important PMM features like Dashboards, QAN, Advisor, Percona Alerting, Backups. 

For more information about working with clusters in PMM, see **Dabases** topic in the [PMM documentation](https://docs.percona.com/percona-monitoring-and-management/dbaas/databases.html).