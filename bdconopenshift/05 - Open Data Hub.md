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

One possible use of analytics is an end-to-end example of Fraud Detection and Scoring using [Red Hat OpenShift](https://www.openshift.com/), [SQL Server Big Data Clusters](https://docs.microsoft.com/en-us/sql/big-data-cluster/big-data-cluster-overview?view=sql-server-ver15#:~:text=Kubernetes%20concepts%20%20%20%20Term%20%20,the%20atomic%20deployment%20unit%20of%20K%20...%20), and the [Open Data Hub project](https://opendatahub.io/). Our datasets involve a sample financial system database, and [sample Credit Card transations from this location](https://www.kaggle.com/isaikumar/creditcardfraud). For instance, a financial institution may wish to perform Extract, Load and Transform (ELT) and model testing and creation locally in a secure environment they control. But they want to "enrich" that process with outside interests, such as remote workers or perhaps even an entirely different organization.

In this scenario, You can incorporate [Red Hat Open Data Hub](https://opendatahub.io/) for a complete solution. Open Data Hub is a blueprint for building an AI as a service platform on Red Hat's Kubernetes-based OpenShift® Container Platform and Ceph Object Storage. It inherits from upstream efforts such as Kafka/Strimzi and Kubeflow, and is the foundation for Red Hat's internal data science and AI platform. Data scientists can create models using Jupyter notebooks, and select from popular tools such as TensorFlow™, scikit-learn, Apache Spark™ and more for developing models. Teams can spend more time solving critical business needs and less on installing and maintaining infrastructure with the Open Data Hub.

This is the diagram of that potential architecure, and the data progression is described below:

<br>

<img style="height: 400; box-shadow: 0 4px 8px 0 rgba(0, 0, 0, 0.2), 0 6px 20px 0 rgba(0, 0, 0, 0.19);" src="https://github.com/microsoft/sqlworkshops-bdconopenshift/blob/main/graphics/SampleArchitecture.png?raw=true">

<br>

The data flow starts with standard On-Line Transaction Processing (OLTP) data entered into the database, and then Credit Card Transactions streamed from multiple commercial locations to a binary-store in a cloud provider. 

<br>
<h2><img style="float: left; margin: 0px 15px 15px 0px;" src="../graphics/pencil2.png">5.2 Solution Walkthrough</h2>

If you are taking this course in-class, the instructor will walk through this example with you. If you are taking it online, the steps below will lead you through creating your own example solution. The documentation and other references you have seen throughout this course will help you build your solution.
<br>


<p><img style="float: left; margin: 0px 15px 15px 0px;" src="../graphics/point1.png"><b>Activity: Build an End-To-End Analytics Solution with SQL Server Big Data Clusters and Red Had Open Data Hub</b></p>

 - Acting as the IT Department at the organization, set up a Red Hat OpenShift cluster (This should already be complete, you can review your solution.)
 - Acting as the IT Department, install a SQL Server Big Data Cluster on the OpenShift environment, and document the endpoints and security for communication to the appropriate developers and engineers (This should already be complete, you can review your solution.)
 - Acting as the Data Engineer, create an Extract, Load and Transform (ELT) process using Spark code in a Jupyter Notebook to ingest data from the cloud binary store into the Storage Pool HDFS location. [Example here](https://docs.microsoft.com/en-us/sql/big-data-cluster/tutorial-data-pool-ingest-spark?view=sql-server-ver15)
 - Acting as the Database administrator, use PolyBase in SQL Server to create an External Table which allows access to the HDFS data, joining it with OLTP Database Tables to create a query and reporting feature for Line-Of-Business users. [Example here](https://docs.microsoft.com/en-us/sql/big-data-cluster/tutorial-query-hdfs-storage-pool?view=sql-server-ver15)
 - Acting as the Data Scientist, use those data sets to [experiment, train, and persist a Fraud Detection model](https://www.kaggle.com/jayeshbali/credit-card-fraud-detection) using a PySpark Notebook in the Storage Pool, and deploying the resulting model to the App Pool. [Application Pool example here](https://docs.microsoft.com/en-us/sql/big-data-cluster/concept-application-deployment?view=sql-server-ver15)
 - Acting as the Data Engineer or Developer, use the trained model with Open Data Hub tools to [deploy an intelligent application for Credit Card Fraud Detection](06%20-%20CCFD%20with%20ODH.md) inside OpenShift.
 - Optional: Convert the model to an intermediate format using ONNX. [Examples here](https://github.com/onnx/tutorials#:~:text=Converting%20to%20ONNX%20format%20%20%20%20Framework,%20%20built-in%20%2011%20more%20rows) 
 - Optional: Convert the model from ONNX to Tensorflow to be ingested to the Open Data Hub environment for addition scoring targets and for further analysis, combining further data sets for more permutations. [Example here](https://opendatahub.io/docs/advanced-tutorials/data-exploration.html)  

<p style="border-bottom: 1px solid lightgrey;"></p>

<p><img style="margin: 0px 15px 15px 0px;" src="../graphics/owl.png"><b>For Further Study</b></p>
<ul>
    <li><a href="https://opendatahub.io/docs.html" target="_blank">You can learn more about Open Data Hub and how to ingest a model at this reference.</a></li>
</ul>

Congratulations! You have completed this workshop. You now have the tools, assets, and processes you need to extrapolate this information into other applications.
