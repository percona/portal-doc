# Launch a Percona Monitoring and Management (PMM) environment

Test-drive PMM from within Percona Platform by generating a free Kubernetes cluster, automatically provisioned with a PMM server, where you can try QAN, DBaaS, Advisor, Alerts and all the features that PMM has to offer.

PMM is an open-source database monitoring and management tool for MySQL, PostgreSQL, and MongoDB. It provides the observability required to understand database health while offering actionable insights to remediate database incidents or performance issues.  

You can create one free Kubernetes environment per day. These ready-to-go environments are ideal for testing out PMM in a native Kubernetes experience and have:

-  3 worker nodes
-  4 CPUs/8GB of RAM
-  3 hours availability

To launch a free PMM environment:

1. In the **PMM Demo** tab, select **Launch PMM environment**. With that, the cluster is provisioned. Within a few minutes, it’ll be ready to use.
2. Once the cluster is created, click **Access PMM environment**.

To test Percona DBaaS on your new cluster:

1. Go to your PMM instance and click <i class="uil uil-database"></i> **DBaaS** on the left menu.
2. Open the **Kubernetes Cluster** tab. This shows your new Kubernetes cluster as **Active**.
3. Click **Create DB cluster** to create the cluster for PMM monitoring.
4. Choose whether you want to create a MySQL or MongoDB database.
5. Verify the values in  the **Advanced Settings** and MySQL Configurations panels.
6. In the **Network and Security** panel, make sure that you enable **Expose** to make this DB cluster available outside of the Kubernetes cluster. If you want the cluster to be accessible on the Internet, also enable the **Internet Facing** option.
7. Click **Create Cluster** to create your cluster. Theis displays the **DB Cluster tab** with details about your new cluster. 
8.  In the **Name** column, click on the bars icon <i class="uil uil-graph-bar"></i> next to the cluster name to open the Custer Summary Dashboard where you can start monitoring your database server using the available PMM metrics.
9. Use the menu on the left side to explore other important PMM features like Dashboards, QAN, Advisor, Percona Alerting, Backups. 

For more information about working with clusters in PMM, see **Dabases** topic in the [PMM documentation](https://docs.percona.com/percona-monitoring-and-management/dbaas/databases.html).