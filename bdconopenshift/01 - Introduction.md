![](../graphics/microsoftlogo.png)

# Workshop: Architecting SQL Server Big Data Cluster Solutions on Red Hat OpenShift

#### <i>A Microsoft Course from the SQL Server team</i>

<p style="border-bottom: 1px solid lightgrey;"></p>

<img style="float: left; margin: 0px 15px 15px 0px;" src="../graphics/textbubble.png"> <h2>01 Introduction and Use-Case</h2>

In this workshop you'll cover setting up a Red Hat OpenShift Cluster on the Microsoft Azure platform, using [Microsoft Azure Red Hat OpenShift](https://docs.microsoft.com/en-us/azure/openshift/intro-openshift) (ARO). You'll get a quick refresher on OpenShift concepts, and a review of the foundations of the SQL Server Big Data Cluster Platform.

In each module you'll get more references, which you should follow up on to learn more. Also watch for links within the text - click on each one to explore that topic.

(<a href="https://github.com/microsoft/sqlworkshops-bdconopenshift/blob/main/bdconopenshift/00%20-%20Pre-Requisites.md" target="_blank">Make sure you check out the <b>Pre-Requisites</b> page before you start</a>. You'll need all of the items loaded there before you can proceed with the workshop.)

<p style="border-bottom: 1px solid lightgrey;"></p>

<h2><img style="float: left; margin: 0px 15px 15px 0px;" src="../graphics/pencil2.png">1.1 Red Hat OpenShift Concepts</h2>

<br>

Red Hat® OpenShift® is a hybrid cloud, enterprise Kubernetes application platform. [You can view a short overview video here](https://www.openshift.com/learn/what-is-openshift#). Azure Red Hat OpenShift is a platform for developing and running containerized applications. It is designed to allow applications and the data centers that support them to expand from just a few machines and applications to thousands of machines that serve millions of clients.

<br>

<img style="height: 400; box-shadow: 0 4px 8px 0 rgba(0, 0, 0, 0.2), 0 6px 20px 0 rgba(0, 0, 0, 0.19);" src="https://www.openshift.com/hubfs/images/illustrations/openshift-container-platform-stack_desktop.svg">

<br>

### Architecture 

Although OpenShift is based on Kubernetes, there are differences in the way it is architected.  Nodes, Pods, and Storage are similar to Kubernetes, with slight differences.The table below illustrates a few major concepts in OpenShift and contains references to learn more. 

<table style="tr:nth-child(even) {background-color: #f2f2f2;}; text-align: left; display: table; border-collapse: collapse; border-spacing: 5px; border-color: gray;">

  <tr><td style="background-color: AliceBlue; color: black;"><b>Concept</b></td><td style="background-color: AliceBlue; color: black;"><b>Descroption</b></td></tr>

  <tr><td><a href="https://docs.openshift.com/container-platform/4.6/architecture/architecture.html" target="_blank">RHCOS </a></td><td> OpenShift Container Platform uses Red Hat Enterprise Linux CoreOS (RHCOS), a container-oriented operating system that combines some of the best features and functions of the CoreOS and Red Hat Atomic Host operating systems</td></tr>
  
  <tr><td style="background-color: AliceBlue; color: black;"><a href="https://docs.openshift.com/container-platform/4.6/applications/projects/working-with-projects.html" target="_blank">Projects </a> </td><td td style="background-color: AliceBlue; color: black;"> Projects encapsulate a Namespace, and access to the Namespace is controlled through a Project through an authentication and authorization model based on Users and Ggroups. This allows Projects to separate Namespaces</td></tr>

  <tr><td><a href="https://docs.openshift.com/container-platform/4.6/architecture/control-plane.html" target="_blank">Control Plane </a></td><td> The Control Plane are a series of machines that manage the OpenShift Container Platform cluster</td></tr>

  <tr><td style="background-color: AliceBlue; color: black;"><a href="https://docs.openshift.com/container-platform/4.6/operators/understanding/olm-what-operators-are.html" target="_blank">Operators </a> </td><td td style="background-color: AliceBlue; color: black;"> Operators are a method of packaging, deploying, and managing a Kubernetes application</td></tr>

  <tr><td><a href="https://docs.openshift.com/container-platform/4.6/architecture/control-plane.html" target="_blank">Control Plane </a></td><td> The Control Plane are a series of machines that manage the OpenShift Container Platform cluster</td></tr>

  <tr><td style="background-color: AliceBlue; color: black;"><a href="https://github.com/microsoft/sqlworkshops-bdconopenshift/blob/main/bdconopenshift/03%20-%20Deployment.md" target="_blank">Web Console and the <i>oc</i> command</a> </td><td td style="background-color: AliceBlue; color: black;"> The primary graphical interface for OpenShift is the web console, a Pod that runs on the master instance. The <a href="https://docs.openshift.com/container-platform/4.6/cli_reference/openshift_cli/usage-oc-kubectl.html" target="_blank"><i>oc</i> command is the primary command-line interface for OpenShift</a>, similar to the kubectl command in Kubernetes, which is also still availability for backwards-compatibility </td></tr>  

  <tr><td><a href="https://www.redhat.com/cms/managed-files/cl-container-security-openshift-cloud-devops-tech-detail-f7530kc-201705-en.pdf?intcmp=701f2000000RQykAAG&extIdCarryOver=true&sc_cid=701f2000001OH7iAAG" target="_blank">Security </a></td><td> Red Hat OpenShift has higher security requirements than Kubernetes. The primary difference is that "run as root" is not permitted on OpenShift</td></tr>
  
  <tr><td style="background-color: AliceBlue; color: black;"><a href="https://docs.openshift.com/container-platform/4.6/networking/routes/route-configuration.html" target="_blank">Networking </a> </td><td td style="background-color: AliceBlue; color: black;"> The OpenShift default Router is an HAProxy container providing reverse proxy capabilities.
A Route is defines rules to apply to incoming connections </td></tr>  

</table>

Other enhancements to Kubernetes in OpenShift Container Platform include improvements in software defined networking (SDN), authentication, log aggregation, monitoring, and routing. OpenShift Container Platform also offers a comprehensive web console and the custom OpenShift CLI (oc) interface.


<p><img style="float: left; margin: 0px 15px 15px 0px;" src="../graphics/point1.png"><b>Activity: Review Primary Concepts</b></p>

In this Activity you will review a course on using Azure Red Hat OpenShift (ARO) to create a simple application. You may follow the steps or simply read through them to familiarize yourself with the platform you will use for this training. 

<p><img style="margin: 0px 15px 15px 0px;" src="../graphics/checkmark.png"><b>Steps</b></p>

<a href="https://aroworkshop.io/" target="_blank"><img style="margin: 0px 15px 15px 0px;" src="../graphics/checkbox.png">Click to open this resource</a>, and follow/read the steps you see there.

<p style="border-bottom: 1px solid lightgrey;"></p>

<h2><img style="float: left; margin: 0px 15px 15px 0px;" src="../graphics/pencil2.png">1.2 SQL Server Big Data Clusters review</h2>

<br>

SQL Server 2019's Big Data Clusters feature can use the OpenShift platform to deploy the power of SQL Server *(RDBMS as OLTP)*, a series of servers used for scaled relational queries *(OLAP and HTAP as Data Lake)* and Spark/HDFS for large data processing *(full scale-out capabilities)* within a single operational/security boundary, ion-prem or in the cloud. It also includes a deployment option for applications *(applications and scoring target)* within the same boundary.    
<br>

<img style="height: 400; box-shadow: 0 4px 8px 0 rgba(0, 0, 0, 0.2), 0 6px 20px 0 rgba(0, 0, 0, 0.19);" src="https://github.com/microsoft/sqlworkshops-bdc/blob/master/graphics/bdc.png?raw=true">

<br>

The table below illustrates the primary components of SQL Server's Big Data Clusters:

<table style="tr:nth-child(even) {background-color: #f2f2f2;}; text-align: left; display: table; border-collapse: collapse; border-spacing: 5px; border-color: gray;">

  <tr><td style="background-color: AliceBlue; color: black;"><b>Component</b></td><td style="background-color: AliceBlue; color: black;"><b>Description</b></td></tr>

  <tr><td><a href="" target="_blank">Controller Service</a></td><td> Description</td></tr>
  
  <tr><td style="background-color: AliceBlue; color: black;"><a href="" target="_blank">SQL Server Master Instance </a> </td><td td style="background-color: AliceBlue; color: black;"> Description</td></tr>

  <tr><td><a href="" target="_blank">Data Pool </a></td><td> Description</td></tr>
  
  <tr><td style="background-color: AliceBlue; color: black;"><a href="" target="_blank">Storage Pool </a> </td><td td style="background-color: AliceBlue; color: black;"> Description</td></tr>

  <tr><td><a href="" target="_blank">Application Pool </a></td><td> Description</td></tr>
  
</table>

More information on SQL Server Big Data Clusters is at [this reference, part of a larger course dedicated to SQL Server Big Data Clusters Architecture](https://github.com/microsoft/sqlworkshops-bdc/blob/master/SQL2019BDC/02%20-%20SQL%20Server%20BDC%20Components.md). 

<p><img style="float: left; margin: 0px 15px 15px 0px;" src="../graphics/point1.png"><b>Activity: TODO: Activity Name</b></p>

TODO: Activity Description and tasks

<p><img style="margin: 0px 15px 15px 0px;" src="../graphics/checkmark.png"><b>Description</b></p>

TODO: Enter activity description with checkbox

<p><img style="margin: 0px 15px 15px 0px;" src="../graphics/checkmark.png"><b>Steps</b></p>

TODO: Enter activity steps description with checkbox

<p style="border-bottom: 1px solid lightgrey;"></p>


<h2><img style="float: left; margin: 0px 15px 15px 0px;" src="../graphics/pencil2.png">1.3  Reference Application Overview</h2>

<br>

Throughout this Lab, we will be using an end-to-end example of Fraud Detection and Scoring using [Red Hat OpenShift](https://www.openshift.com/), [SQL Server Big Data Clusters](https://docs.microsoft.com/en-us/sql/big-data-cluster/big-data-cluster-overview?view=sql-server-ver15#:~:text=Kubernetes%20concepts%20%20%20%20Term%20%20,the%20atomic%20deployment%20unit%20of%20K%20...%20), and the [Open Data Hub project](https://opendatahub.io/). Our datasets involve a sample financial system database, and [sample Credit Card transations from this location](https://www.kaggle.com/isaikumar/creditcardfraud).

This is the diagram of the architecure, and the data progression is described below:

<br>

<img style="height: 400; box-shadow: 0 4px 8px 0 rgba(0, 0, 0, 0.2), 0 6px 20px 0 rgba(0, 0, 0, 0.19);" src="https://github.com/microsoft/sqlworkshops-bdconopenshift/blob/main/graphics/SampleArchitecture.png?raw=true">

<br>

The data flow starts with standard On-Line Transaction Processing (OLTP) data entered into the database, and then Credit Card Transactions streamed from multiple commercial locations to a binary-store in a cloud provider. From there, the data is processed theough the system:

1. The IT Department sets up a Red Hat OpenShift cluster (on-prem or in-cloud)
2. The IT Department installs a SQL Server Big Data Cluster on the OpenShift environment, and communicates the endpoints and security to the appropriate developers and engineers
3. The Data Engineering team creates an Extract-Transform and Load (ETL) process using Spark code in a Jupyter Notebook to ingest data from the cloud binary store into the Storage Pool HDFS location
4. The Database Administration team uses PolyBase in SQL Server to create an External Table which allows access to the HDFS data, joining it with OLTP Database Tables to create a query and reporting feature for Line-Of-Business users
5. The Data Science Team uses multiple data sets to [experiment, train, and persist a Fraud Detection model](https://www.kaggle.com/jayeshbali/credit-card-fraud-detection) using a PySpark Notebook in the Storage Pool, and deploying the resulting model to the App Pool
6. The model is converted to an intermediate format using ONNX
7. The model is converted from ONNX to Tensorflow to be ingested to the Open Data Hub environment for addition scoring targets and for further analysis, combining further data sets for more permutations  

<br>

<p><img style="float: left; margin: 0px 15px 15px 0px;" src="../graphics/point1.png"><b>Activity: TODO: Activity Name</b></p>

TODO: Activity Description and tasks

<p><img style="margin: 0px 15px 15px 0px;" src="../graphics/checkmark.png"><b>Description</b></p>

TODO: Enter activity description with checkbox

<p><img style="margin: 0px 15px 15px 0px;" src="../graphics/checkmark.png"><b>Steps</b></p>

TODO: Enter activity steps description with checkbox

<p style="border-bottom: 1px solid lightgrey;"></p>

<br> 

<p><img style="float: left; margin: 0px 15px 15px 0px;" src="../graphics/point1.png"><b>Deploy a SQL Server Big Data Cluster to Red Hat OpenShift on ARO</b></p>

TODO: Activity Description and tasks

<p><img style="margin: 0px 15px 15px 0px;" src="../graphics/checkmark.png"><b>Description</b></p>

TODO: Enter activity description with checkbox

<p><img style="margin: 0px 15px 15px 0px;" src="../graphics/checkmark.png"><b>Steps</b></p>

- Open [the following reference and follow all steps you see there](https://docs.microsoft.com/en-us/sql/big-data-cluster/deploy-openshift?view=sql-server-ver15). We will return to some of these steps as part of the workshop, so just use the values explained in the documentation.

<p style="border-bottom: 1px solid lightgrey;"></p>


<p><img style="margin: 0px 15px 15px 0px;" src="../graphics/owl.png"><b>For Further Study</b></p>
<ul>
    <li><a href="https://docs.microsoft.com/en-us/azure/openshift/tutorial-create-cluster" target="_blank">A Complete course on setting up an Azure Red Hat OpenShift 4 Cluster is here</a></li>
</ul>

Congratulations! You have completed this workshop on <TODO: Enter workshop name>. You now have the tools, assets, and processes you need to extrapolate this information into other applications.