![](../graphics/microsoftlogo.png)

# Workshop: Architecting SQL Server Big Data Cluster Solutions on Red Hat OpenShift

#### <i>A Microsoft workshop from the SQL Server team</i>

<p style="border-bottom: 1px solid lightgrey;"></p>

<img style="float: left; margin: 0px 15px 15px 0px;" src="../graphics/textbubble.png"> <h2>05 Open Data Hub</h2>

In this workshop, you'll learn how to plan, implement and operate a SQL Server Big Data Cluster on the Red Hat OpenShift platform. This module covers how to leverage work done in a SQL Server Big Data Cluster with the Red Hat Open Data Hub project. 

In each section of this Module you'll get more references, which you should follow up on to learn more. Also watch for links within the text - click on each one to explore that topic.

<a href="https://github.com/microsoft/sqlworkshops-bdconopenshift/blob/main/bdconopenshift/00%20-%20Pre-Requisites.md" target="_blank">Make sure you check out the <b>Pre-Requisites</b> page before you start</a>. You'll need all of the items loaded there before you can proceed with the workshop.

<p style="border-bottom: 1px solid lightgrey;"></p>

<h2><img style="float: left; margin: 0px 15px 15px 0px;" src="../graphics/pencil2.png">5.1  Reference Application Review</h2>

<br>

One possible use of analytics is an end-to-end example of Fraud Detection and Scoring using [Red Hat OpenShift](https://www.openshift.com/), [SQL Server Big Data Clusters](https://docs.microsoft.com/en-us/sql/big-data-cluster/big-data-cluster-overview?view=sql-server-ver15#:~:text=Kubernetes%20concepts%20%20%20%20Term%20%20,the%20atomic%20deployment%20unit%20of%20K%20...%20), and the [Open Data Hub project](https://opendatahub.io/). Our datasets involve a sample financial system database, and [sample Credit Card transations from this location](https://www.kaggle.com/isaikumar/creditcardfraud).

This is the diagram of that potential architecure, and the data progression is described below:

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
<h2><img style="float: left; margin: 0px 15px 15px 0px;" src="../graphics/pencil2.png">5.2 Solution Walkthrough</h2>

If you are taking this course in-class, the instructor will walk through this example with you. If you are taking it online, the steps below will lead you through creating your own example solution.

<br>

<img style="height: 400; box-shadow: 0 4px 8px 0 rgba(0, 0, 0, 0.2), 0 6px 20px 0 rgba(0, 0, 0, 0.19);" src="https://docs.microsoft.com/en-us/sql/big-data-cluster/media/concept-security/cluster_endpoints.png">

<br>

<p><img style="float: left; margin: 0px 15px 15px 0px;" src="../graphics/point1.png"><b>Activity: TODO: Activity Name</b></p>

TODO: Activity Description and tasks

<p><img style="margin: 0px 15px 15px 0px;" src="../graphics/checkmark.png"><b>Description</b></p>

TODO: Enter activity description with checkbox

<p><img style="margin: 0px 15px 15px 0px;" src="../graphics/checkmark.png"><b>Steps</b></p>

TODO: Enter activity steps description with checkbox

<p style="border-bottom: 1px solid lightgrey;"></p>


<p><img style="margin: 0px 15px 15px 0px;" src="../graphics/owl.png"><b>For Further Study</b></p>
<ul>
    <li><a href="url" target="_blank">TODO: Enter courses, books, posts, whatever the student needs to extend their study</a></li>
</ul>

Congratulations! You have completed this workshop on <TODO: Enter workshop name>. You now have the tools, assets, and processes you need to extrapolate this information into other applications.