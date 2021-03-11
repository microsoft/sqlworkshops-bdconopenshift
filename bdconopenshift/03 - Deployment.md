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

<br>

<TODO: Topic Text>

<br>

<p><img style="float: left; margin: 0px 15px 15px 0px;" src="../graphics/point1.png"><b>Activity: <TODO: Determine Topic Activity</b></p>

In this Activity you will review the installation you performed during the pre-requisites section. If you are taking this Workshop in a group environment, you will review these scripts with the instructor. If you are taking this Workshop on your own, ensure you understand each step in the script and configuration; search for any terms or files you are not familiar with. 

<p><img style="margin: 0px 15px 15px 0px;" src="../graphics/checkmark.png"><b><TODO: Step Name</b></p>

 - Open the following reference and review the script you see there: [<TODO: Web Link Title>](https://docs.microsoft.com/en-us/sql/big-data-cluster/connect-to-big-data-cluster?view=sql-server-ver15)

<p style="border-bottom: 1px solid lightgrey;"></p>
<h2><img style="float: left; margin: 0px 15px 15px 0px;" src="../graphics/pencil2.png">3.4 - Implement a security strategy for the solution</h2>

<br>

<TODO: Topic Text>

<br>

<p><img style="float: left; margin: 0px 15px 15px 0px;" src="../graphics/point1.png"><b>Activity: <TODO: Determine Topic Activity</b></p>

In this Activity you will review the installation you performed during the pre-requisites section. If you are taking this Workshop in a group environment, you will review these scripts with the instructor. If you are taking this Workshop on your own, ensure you understand each step in the script and configuration; search for any terms or files you are not familiar with. 

<p><img style="margin: 0px 15px 15px 0px;" src="../graphics/checkmark.png"><b><TODO: Step Name</b></p>

 - Open the following reference and review the script you see there: [<TODO: Web Link Title>](https://docs.microsoft.com/en-us/sql/big-data-cluster/non-root-containers?view=sql-server-ver15)

<p style="border-bottom: 1px solid lightgrey;"></p>
<h2><img style="float: left; margin: 0px 15px 15px 0px;" src="../graphics/pencil2.png">3.5 - Manage the solution using built-in tools for each component, and comprehensive monitoring with Grafana and Kibana</h2>

<br>

<TODO: Topic Text>

<br>

<p><img style="float: left; margin: 0px 15px 15px 0px;" src="../graphics/point1.png"><b>Activity: <TODO: Determine Topic Activity</b></p>

In this Activity you will review the installation you performed during the pre-requisites section. If you are taking this Workshop in a group environment, you will review these scripts with the instructor. If you are taking this Workshop on your own, ensure you understand each step in the script and configuration; search for any terms or files you are not familiar with. 

<p><img style="margin: 0px 15px 15px 0px;" src="../graphics/checkmark.png"><b><TODO: Step Name</b></p>

 - Open the following reference and review the script you see there: [<TODO: Web Link Title>](https://docs.microsoft.com/en-us/sql/big-data-cluster/manage-with-controller-dashboard?view=sql-server-ver15)

<p style="border-bottom: 1px solid lightgrey;"></p>


<p><img style="margin: 0px 15px 15px 0px;" src="../graphics/owl.png"><b>For Further Study</b></p>
<ul>
    <li><a href="url" target="_blank"><TODO: Enter courses, books, posts, whatever the student needs to extend their study></a></li>
</ul>


Next, Continue to <a href="https://github.com/microsoft/sqlworkshops-bdconopenshift/blob/main/bdconopenshift/02%20-%20Planning.md" target="_blank"><i> 02 Planning</i></a>.

<pre>


https://github.com/microsoft/sqlworkshops-bdconopenshift/tree/main/bdconopenshift 

https://docs.openshift.com/container-platform/4.6/welcome/index.html 

https://microsoft.sharepoint.com/teams/redhatmsshare/Shared%20Documents/Forms/AllItems.aspx?id=%2Fteams%2Fredhatmsshare%2FShared%20Documents%2FEngineering%2FOpenShift%2F4%2E2%2DbetaDocs%2Epdf&parent=%2Fteams%2Fredhatmsshare%2FShared%20Documents%2FEngineering%2FOpenShift

https://docs.microsoft.com/en-us/sql/big-data-cluster/deploy-openshift?view=sql-server-ver15

https://docs.microsoft.com/en-us/sql/big-data-cluster/quickstart-big-data-cluster-deploy-aro?view=sql-server-ver15#bdc-sccyaml 

https://github.com/microsoft/sqlworkshops-bdconopenshift/tree/main/bdconopenshift 

</pre>
