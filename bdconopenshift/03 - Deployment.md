![](../graphics/microsoftlogo.png)

# Workshop: Architecting SQL Server Big Data Cluster Solutions on Red Hat OpenShift

#### <i>A Microsoft workshop from the SQL Server team</i>

<p style="border-bottom: 1px solid lightgrey;"></p>

<img style="float: left; margin: 0px 15px 15px 0px;" src="../graphics/textbubble.png"> <h2>03 Deployment and Operation</h2>

In this workshop, you'll learn how to plan, implement and operate a SQL Server Big Data Cluster on the Red Hat OpenShift platform. This module covers how to install your Big Data Cluster. 

In each section of this Module you'll get more references, which you should follow up on to learn more. Also watch for links within the text - click on each one to explore that topic.

<a href="https://github.com/microsoft/sqlworkshops-bdconopenshift/blob/main/bdconopenshift/00%20-%20Pre-Requisites.md" target="_blank">Make sure you check out the <b>Pre-Requisites</b> page before you start</a>. You'll need all of the items loaded there before you can proceed with the workshop.

<p style="border-bottom: 1px solid lightgrey;"></p>

<h2><img style="float: left; margin: 0px 15px 15px 0px;" src="../graphics/pencil2.png">3.1 - Implement the proper licensing for the solution</h2>

<br>

There are two licensing models you need to consider for your solution. The first is for the Red Hat OpenShift platform you choose. In general, on-premises installation licensing follows whatever you have set up with your Red Hat corporate relationship. You can find [more general licensing information here](https://www.openshift.com/products/pricing/).

Deploying to a Cloud environment is usually more simplistic for licensing. In general, you will use a "pay as you go" model, where you pay by the capacity you use, and not break out the licensing costs separately. In this course you will deploy a sample solution on Microsoft Azure Red Hat OpenShift, [and the pricing for that platform is located here.](https://azure.microsoft.com/en-us/pricing/details/openshift/) 
<br>

<p><img style="float: left; margin: 0px 15px 15px 0px;" src="../graphics/point1.png"><b>Activity: Learn the Specifics of Licensing SQL Server Big Data Clusters</b></p>

In this Activity you will review the licensing for SQL Server Big Data Cluster, and next you will perform the Installation on the Microsoft Azure OpenShift (ARO) platform. If you are taking this Workshop in a group environment, you will review these scripts with the instructor. If you are taking this Workshop on your own, ensure you understand each step in the script and configuration; search for any terms or files you are not familiar with. 

<p><img style="margin: 0px 15px 15px 0px;" src="../graphics/checkmark.png"><b>Review Licensing Aspects</b></p>

 - [Open the following reference and review the information you see there on Big Data Clusters licensing.](https://techcommunity.microsoft.com/t5/sql-server/optimize-tco-with-new-sql-server-software-assurance-benefits-for/ba-p/1123731?WT.mc_id=dataexposed-c9-niner)
 - [Open the following reference and watch the video you see there for licensing your solution.](https://channel9.msdn.com/Shows/Data-Exposed/SQL-Server-Licensing-Big-Data-Clusters--Data-Exposed)

<p style="border-bottom: 1px solid lightgrey;"></p>


<h2><img style="float: left; margin: 0px 15px 15px 0px;" src="../graphics/pencil2.png">3.2 - Deploy a SQL Server Big Data Cluster to Red Hat OpenShift</h2>

<br>

With the preparation so far, you're ready to start the deployment you have designed. Keep in mind that for this course you are using the Microsoft Azure Red Hat OpenShift (ARO) environment, and so other designs will have different deployment options. 

[Full instructions for all types of Red Hat OpenShift deployments are located here.](https://docs.microsoft.com/en-us/sql/big-data-cluster/deploy-openshift?view=sql-server-ver15) For the next activity, you will use the pre-requisites you installed to deploy your cluster. Total deployment time is around 30 minutes.  

<br>

<p><img style="float: left; margin: 0px 15px 15px 0px;" src="../graphics/point1.png"><b>Activity: Deploy a SQL Server Big Data Cluster on Azure Red Hat OpenShift (ARO)</b></p>

If you are taking this Workshop in a group environment, you will review this process with the instructor. If you are taking this Workshop on your own, ensure you understand each step in theinstallation and configuration; search for any terms or files you are not familiar with. 

<p><img style="margin: 0px 15px 15px 0px;" src="../graphics/checkmark.png"><b>Deployment</b></p>

 - [Open the following reference and follow the steps you see there](https://docs.microsoft.com/en-us/sql/big-data-cluster/quickstart-big-data-cluster-deploy-aro?view=sql-server-ver15#prerequisites)

<p style="border-bottom: 1px solid lightgrey;"></p>
<h2><img style="float: left; margin: 0px 15px 15px 0px;" src="../graphics/pencil2.png">3.3 - Leverage the Endpoints and Interfaces for the solution</h2>

Now that you have installed your cluster, you can connect to the *endpoints* it provides. You can list these endpoints in the Azure Data Studio tool:

<br>
<img src="https://docs.microsoft.com/en-us/sql/big-data-cluster/media/manage-with-controller-dashboard/controller-dashboard.png?view=sql-server-ver15">
<br>

You can also list the endpoints using the `azdata` command. Here is an example deployment and the values returned from the following command:

`azdata bdc endpoint list`

<Table>
    <tr><th>Endpoint Purpose</th><th>Example IP and Port</th></tr>
    <tr><td>SQL Server Master Instance Front-End</td><td>10.1.1.1,31433</td></tr>
    <tr><td>Cluster Management Service</td><td>https://10.1.1.2:30080</td></tr>
    <tr><td>Management Proxy</td><td>https://10.1.1.3:30777</td></tr>
    <tr><td>Metrics Dashboard</td><td>https://10.1.1.3:30777/grafana/d/xxxxx</td></tr>
    <tr><td>Log Search Dashboard</td><td>https://10.1.1.3:30777/kibana/app/kibana#/discover</td></tr>
    <tr><td>Gateway to access HDFS files, Spark</td><td>https://10.1.1.4:30443</td></tr>
    <tr><td>Proxy for running Spark statements, jobs, applications</td><td>https://10.1.1.5:30443/gateway/default/livy/v1</td></tr>
    <tr><td>Spark Jobs Management and Monitoring Dashboard</td><td>https://10.1.1.5:30443/gateway/default/sparkhistory</td></tr>
    <tr><td>HDFS File System Proxy</td><td>https://10.1.1.5:30443/gateway/default/webhdfs/v1</td></tr>
    <tr><td>Spark Diagnostics and Monitoring Dashboard</td><td>https://10.1.1.5:30443/gateway/default/yarn</td></tr>
    <tr><td>Application Proxy</td><td>https://10.1.1.6:30778</td></tr>
</table>

<br>

<p><img style="float: left; margin: 0px 15px 15px 0px;" src="../graphics/point1.png"><b>Activity: Connect to your Big Data Cluster deployment</b></p>

In this Activity you will connect to the cluster you deployed. You'll use two methods, the Azure Data Studio and the `azdata` command. 

<p><img style="margin: 0px 15px 15px 0px;" src="../graphics/checkmark.png">Connect to your BDC using Azure Data Studio and azdata</b></p>

 - [Open the following reference and follow the instructions you see there to connect to your BDC using Azure Data Studio](https://docs.microsoft.com/en-us/sql/big-data-cluster/connect-to-big-data-cluster?view=sql-server-ver15)
 - [Open the following reference and follow the instructions you see there to connect to your BDC using azdata to see the status](https://docs.microsoft.com/en-us/sql/azdata/reference/reference-azdata-bdc-status?view=sql-server-ver15)

<p style="border-bottom: 1px solid lightgrey;"></p>
<h2><img style="float: left; margin: 0px 15px 15px 0px;" src="../graphics/pencil2.png">3.4 - Implement a security strategy for the solution</h2>

<br>

Installing SQL Server Big Data Clusters on Red Hat OpenShift comes with additional security considerations, defined in the custom security context constraint (SCC). You can find the comnplete SCC here, and you will review that in the Activities below. The custom SCC for BDC is based on the built-in nonroot SCC in OpenShift, with additional permissions. 

> NOTE: SQL Server 2019 CU5 introduces support for non-root containers. The platform implementation is safer by ensuring that all container applications running within BDC are started as non-root users by default, on all supported platforms. These capabilities are available for all new deployments using the SQL Server 2019 CU5 corresponding image tag. If you are taking this workshop, you will deploy CU5 or higher. 

For a complete review of security aspects of BDC on OpenShift you will review two resources - if you are in-class, you will work through these with the instructor, if you are taking this workshop on your own, follow through the resources indicated below. 

<br>

<p><img style="float: left; margin: 0px 15px 15px 0px;" src="../graphics/point1.png"><b>Activity: Review SCC and Security Documentation</b></p>

In this Activity you will review the installation you performed during the pre-requisites section. If you are taking this Workshop in a group environment, you will review these scripts with the instructor. If you are taking this Workshop on your own, ensure you understand each step in the script and configuration; search for any terms or files you are not familiar with. 

 - [Open the following reference and review the information you see there.](https://docs.microsoft.com/en-us/sql/big-data-cluster/non-root-containers?view=sql-server-ver15)
 - [Open the following reference and review the Red Hat OpenShift security documentation you see there.](https://docs.openshift.com/container-platform/4.3/authentication/managing-security-context-constraints.html)
 - [Open the following reference and review the security white-paper you see there.](https://aka.ms/sql-bdc-openshift-security)
 - [Open the following reference and review the SCC depolyment variables you see there.](https://docs.microsoft.com/en-us/sql/big-data-cluster/deploy-openshift?view=sql-server-ver15#bdc-sccyaml-file)

<p style="border-bottom: 1px solid lightgrey;"></p>
<h2><img style="float: left; margin: 0px 15px 15px 0px;" src="../graphics/pencil2.png">3.5 - Manage the solution using built-in tools for each component</h2>

<br>

There are a few primary tools you will use to manage your deployment:

- oc - Manage Red Hat OpenShift cluster utility (Command Line) [(Reference)](https://docs.openshift.com/container-platform/4.7/cli_reference/openshift_cli/getting-started-cli.html)
- Red Hat OpenShift Container Platform Dashboard (Graphical Interface) [(Reference)](https://docs.openshift.com/container-platform/4.7/web_console/using-dashboard-to-get-cluster-information.html)
- azdata - SQL Server Big Data Clusters utility (Command Line) [(Reference)](https://docs.microsoft.com/en-us/sql/azdata/reference/reference-azdata?view=sql-server-ver15)
- Azure Data Studio - Coding, monitoring and management of the SQL Server and Spark environments (Graphical Interface) [(Reference)](https://docs.microsoft.com/en-us/sql/big-data-cluster/manage-with-controller-dashboard?view=sql-server-ver15)

<br>

<p><img style="float: left; margin: 0px 15px 15px 0px;" src="../graphics/point1.png"><b>Activity: Use various utilities and tools to connect to your Big Data Cluster</b></p>

In this Activity you will review the installation you performed during the pre-requisites section. If you are taking this Workshop in a group environment, you will review these scripts with the instructor. If you are taking this Workshop on your own, ensure you understand each step in the script and configuration; search for any terms or files you are not familiar with. 

<p><img style="margin: 0px 15px 15px 0px;" src="../graphics/checkmark.png"><b><TODO: Step Name</b></p>

 - Using the `oc` utility, get the description and status of your Big Data Cluster OpenShift environment. What pods are listed?
 - Using the `azdata` utility, list the IP address and ports for your Big Data Cluster. 
 - Using the `Azure Data Studio` tool, connect to your SQL Server Instance in your Big Data Cluster and get the release number for the Instance. 
 - Using the `OpenShift Container Platform Dashboard` tool, show the Persistent Volumes on your cluster.

<p style="border-bottom: 1px solid lightgrey;"></p>

<p><img style="margin: 0px 15px 15px 0px;" src="../graphics/owl.png"><b>For Further Study</b></p>
<ul>
    <li>https://docs.microsoft.com/en-us/sql/big-data-cluster/view-cluster-status?view=sql-server-ver15#manage-and-operate-with-tools</li>
    <li>https://dzone.com/articles/top-kubernetes-health-metrics-you-must-monitor</li> 
    <li>https://docs.openshift.com/container-platform/4.6/welcome/index.html</li> 
    <li>https://docs.microsoft.com/en-us/sql/big-data-cluster/deploy-openshift?view=sql-server-ver1</li>
    <li>https://docs.microsoft.com/en-us/sql/big-data-cluster/quickstart-big-data-cluster-deploy-aro?view=sql-server-ver15#bdc-sccyaml</li> 
</ul>


Next, Continue to <a href="https://github.com/microsoft/sqlworkshops-bdconopenshift/blob/main/bdconopenshift/04%20-%20Optimization.md" target="_blank"><i> 04 Optimization</i></a>.
