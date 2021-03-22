![](../graphics/microsoftlogo.png)

# Workshop: Architecting SQL Server Big Data Cluster Solutions on Red Hat OpenShift

#### <i>A Microsoft workshop from the SQL Server team</i>

<p style="border-bottom: 1px solid lightgrey;"></p>

<img style="float: left; margin: 0px 15px 15px 0px;" src="../graphics/textbubble.png"> <h2>04 Optimization</h2>

In this workshop, you'll learn how to plan, implement and operate a SQL Server Big Data Cluster on the Red Hat OpenShift platform. This module covers how to optimize your advanced analytics system. 

In each section of this Module you'll get more references, which you should follow up on to learn more. Also watch for links within the text - click on each one to explore that topic.

<a href="https://github.com/microsoft/sqlworkshops-bdconopenshift/blob/main/bdconopenshift/00%20-%20Pre-Requisites.md" target="_blank">Make sure you check out the <b>Pre-Requisites</b> page before you start</a>. You'll need all of the items loaded there before you can proceed with the workshop.

<p style="border-bottom: 1px solid lightgrey;"></p>

<h2><img style="float: left; margin: 0px 15px 15px 0px;" src="../graphics/pencil2.png">4.1 - Setting a Baseline</h2>

<br>

Performance tuning for any system involves identifying bottlenecks, deviations and other issues, and experimenting with corrections and mitigations to bring the system back to expected performance. This process assumes you have a baseline of metrics to compare the suspected deviation. Some baselines are inherent, meaning there are published norms for the components the system contains. Others are based on the configuration in the deployed system, and must be gathered manually, and often periodically. 

A SQL Server Big Data Cluster (BDC) is made up of several components, and this workshop covers one of the platforms it uses, Red Hat OpenShift, which is also made up of multiple components. Each of these has various metrics that are meaningful in a given deployment configuration, and each has a different collection method. The `Azure Data Studio` tool contains a set of Jupyter Notebooks that walk through the various components of a BDC and collects the logs for the components, including some that have performance metrics. In the sections that follow, you'll use other tools to collect metrics not covered by these Notebooks. 

One artifact of a Jupyter Notebook is that when each Cell is run, the results are retained within the Notebook when it is saved. Since these are text-based JSON files, they can be saved and compared later to establish the deviation for performance.

> NOTE: There are surface areas not covered by the Management Notebooks in Azure Data Studio, such as your hardware environment and all metrics exposed by the Red Hat OpenShift cluster platform. If you are deploying within a Cloud provider such as Microsoft Azure, other metrics and tools are available as well. You should consider all of these environmental factors wehn collecting and archiving your baseline metrics. 

<br>

<p><img style="float: left; margin: 0px 15px 15px 0px;" src="../graphics/point1.png"><b>Activity: Use Management Notebooks in Azure Data Studio to establish a Metrics Baseline</b></p>

In this Activity you will collect and review logs for the installation you performed earlier. If you are taking this Workshop in a group environment, you will review these steps with the instructor. If you are taking this Workshop on your own, ensure you understand each step in the script and configuration; search for any terms or files you are not familiar with. 

<p><img style="margin: 0px 15px 15px 0px;" src="../graphics/checkmark.png"><b>Run and Save Management Notebooks in Azure Data Studio</b></p>

 - [Open the following reference and review the information you see there.](https://<TODO: Web Link>)
 - Locate and run at least one Notebook that deals with a performance vector. Save that Notebook and review its contents.
 
<p style="border-bottom: 1px solid lightgrey;"></p>

<h2><img style="float: left; margin: 0px 15px 15px 0px;" src="../graphics/pencil2.png">4.2 - Monitoring the system Real-Time</h2>

<br>

You have three primary sets of tools you can use to monitor the BDC environment as it is running:

- Command-line tools (oc and azdata, along with the Spark commands)
- Graphical single-component tools (Such as the Red Hat Dashboard, Spark Dashboard, and SQL Server graphical monitoring tools)
- Grafana/Kibana

Your BDC deployment comes with two graphical tools `Grafana` and `Kibana`, which provide not only real-time monitoring of various performance metrics and logs, but also the ability to record those metrics as Comma-Separated Value (CSV) files. 

In the activity below, you will use these tools to monitor your system. 

<br>

<p><img style="float: left; margin: 0px 15px 15px 0px;" src="../graphics/point1.png"><b>Activity: Using Grafna and Kibana to Monitor your Deployment</b></p>

In this Activity you will review the Grafana and Kibana tools installed with your deployment, select various metrics, and save the results. If you are taking this Workshop in a group environment, you will review these steps with the instructor. If you are taking this Workshop on your own, ensure you understand each step in the script and configuration; search for any terms or files you are not familiar with. 

<p><img style="margin: 0px 15px 15px 0px;" src="../graphics/checkmark.png"><b>Review and access Kibana</b></p>

 - [Open the following reference and review the information you see there](https://<TODO: Web Link>)
 - Access Kibana, set a range to gather log data, and export that data as a CSV file.
 
<p><img style="margin: 0px 15px 15px 0px;" src="../graphics/checkmark.png"><b>Review and access Grafana</b></p>

 - [Open the following reference and review the information you see there](https://<TODO: Web Link>)
 - Access Graphana, open the Master 0-0 Pod, and export that data as a CSV file.


<p style="border-bottom: 1px solid lightgrey;"></p>

<h2><img style="float: left; margin: 0px 15px 15px 0px;" src="../graphics/pencil2.png">4.3 - Optimizing the System based on Monitoring the Baseline</h2>

<br>

Once you have established a baseline from defined norms or collected a baseline during a typical performance period, you are ready to compare that baseline to a new collection measurement to narrow down the issue to a given component. At that point, you're able to take corrective mitigations based on your measurements.

It is important to understand that there are several inter-related components in a complex analytics system, so a thorough understanding of not only each component but also how they interact with common subsystems (such as storage or CPU) is essential. In the activity that follows,you will explore a few resources that serve as a starting point for this level of understanding.

<br>

<p><img style="float: left; margin: 0px 15px 15px 0px;" src="../graphics/point1.png"><b>Activity: Locate resources for creating performance mitigations</b></p>

In this Activity you will review several resources for the components within an analytics environment.  

<p><img style="margin: 0px 15px 15px 0px;" src="../graphics/checkmark.png"><b>Review and add Resources</b></p>

- In the `For Further Study` section that follows, there are several links to Performance Tuning for the major components deployed in a BDC, as well as various platform reference. Review and bookmark each of these.
- Locate performance references for the platform (such as Microsoft Azure or on-prem) where you plan to deploy your production BDC and bookmark those as well.

<p><img style="margin: 0px 15px 15px 0px;" src="../graphics/owl.png"><b>For Further Study</b></p>
<ul>
    <li><a href="https://docs.microsoft.com/en-us/sql/big-data-cluster/performance-guidelines-tuned?view=sql-server-ver15" target="_blank">Performance Tuning Guide for SQL Server Big Data Clusters</a></li>
    <li><a href="https://access.redhat.com/documentation/en-us/openshift_container_platform/4.6/html/scalability_and_performance/index" target="_blank">Performance Tuning for Red Hat OpenShift Clusters</a></li>
    <li><a href="https://docs.microsoft.com/en-us/sql/relational-databases/performance/monitor-and-tune-for-performance?view=sql-server-ver15" target="_blank">Performance Tuning Guide for SQL Server</a></li>
    <li><a href="https://spark.apache.org/docs/latest/tuning.html" target="_blank">Performance Tuning Guide for Spark</a></li>
</ul>

Next, Continue to <a href="https://github.com/microsoft/sqlworkshops-bdconopenshift/blob/main/bdconopenshift/05%20-%20Open%20Data%20Hub.md" target="_blank"><i> 05 Open Data Hub</i></a>.