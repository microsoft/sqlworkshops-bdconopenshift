![](../graphics/microsoftlogo.png)

# Workshop: Architecting SQL Server Big Data Cluster Solutions on Red Hat OpenShift

#### <i>A Microsoft Course from the SQL Server team</i>

<p style="border-bottom: 1px solid lightgrey;"></p>

<img style="float: left; margin: 0px 15px 15px 0px;" src="../graphics/textbubble.png"> <h2>00 Pre-Requisites</h2>

The "Workshop: Architecting SQL Server Big Data Cluster Solutions on Red Hat OpenShift" workshop is taught using the following components, which you will create and configure in the sections that follow. During the course, you will deploy a SQL Server Big Data Cluster to Microsoft Azure Red Hat OpenShift (ARO), or if in-class the instructor may provide an environment for you. 

*Note that all following activities must be completed prior to class - there will not be time to perform these operations during the workshop. Unless you are explicitly told you will be provided an account by the instructor in the invitation to this workshop, you must have your Microsoft Azure account and Workstation Machine set up before you arrive at class.*

**Knowledge**

You should be familiar with the following concepts, products, and technologies prior to taking this workshop. If you are new to any of these, complete the following courses and studies:

<table style="tr:nth-child(even) {background-color: #f2f2f2;}; text-align: left; display: table; border-collapse: collapse; border-spacing: 2px; border-color: gray;">

  <tr><th style="background-color: #1b20a1; color: white;">Technology</th> <th style="background-color: #1b20a1; color: white;">Description</th></tr>

  <tr><td>Linux</td><td><a href="https://www.digitalocean.com/community/tutorial_series/getting-started-with-linux" target="_blank">Online course using community Tutorials</a></td></tr>
  <tr><td>Containers</td><td><a href="https://docker-curriculum.com/" target="_blank">Online course from Docker</a></td></tr>
  <tr><td>Kubernetes</td><td><a href="https://www.katacoda.com/courses/kubernetes" target="_blank">Online course with free online environment from Katacoda</a></td></tr>
  <tr><td>Red Hat OpenShift Platform</td><td><a href="https://learn.openshift.com/" target="_blank">Online course from Red Hat with free online environment</a></td></tr>
  <tr><td>Microsoft SQL Server</td><td><a href="https://www.microsoft.com/en-us/learning/sql-training.aspx" target="_blank">Multiple training options from Microsoft</a></td></tr>
  <tr><td>Microsoft SQL Server Big Data Clusters</td><td><a href="https://github.com/Microsoft/sqlworkshops-bdc" target="_blank">Online workshop from Microsoft</a></td></tr>

</table>

<br>
<br>

**Platform**

Microsoft Azure: This workshop uses the Microsoft Azure platform to host the Red Hat Openshift cluster (using the Azure Red Hat OpenShift (ARO) Service), and optionally you can deploy a system there to act as a workstation. You can use a free Azure account, an MSDN Account, your own account, or potentially one provided for you, as long as you can create about $100.00 (U.S.) worth of assets.

<p><img style="float: left; margin: 0px 15px 15px 0px;" src="../graphics/point1.png">Activity: Set up a Microsoft Azure Account</p>

You have multiple options for setting up Microsoft Azure account to complete this workshop. You can use a free account, a Microsoft Developer Network (MSDN) account, a personal or corporate account, or in some cases a pass may be provided by the instructor. (Note: for most classes, the MSDN account is best)

*Option 1 - Free Account*
The free account gives you twelve months of time, and a limited amount of resources. Set this up prior to coming to class, and ensure you can access it from the system you will bring to the class.

- [Open this resource, and click the "Start Free" button you see there](https://azure.microsoft.com/en-us/free/)

> NOTE: You can only use the Free subscription once, and it expires in 12 months. Set up your account and create the DSVM per the instructions below, but ensure that you turn off the VM in the Portal to ensure that you do no exceed the cost limits on this account. You will turn it off and on in the classroom per the instructor's directions.*

*Option 2 - Microsoft Visual Studio Account Account*
The best way to take this workshop is to use your [Azure benefits if you have a Visual Studio subscription](https://marketplace.visualstudio.com/subscriptions).

- [Open this resource and click the "Activate your monthly Azure credit" button](https://azure.microsoft.com/en-us/pricing/member-offers/credit-for-visual-studio-subscribers/)

*Option 3 - Use Your Own Account*
You can also use your own account or one provided to you by your organization, but you must be able to create a resource group and create, start, and manage a Data Science Virtual Machine (DSVM) and an Azure AKS cluster. 

*Option 4 - Use an account provided by your instructor*
Your workshop invitation may have instructed you that they will provide a Microsoft Azure or other account for you to use. If so, you will receive instructions.

> Unless you received explicit instructions in your workshop invitations, you much create either a free, MSDN or Personal account. You must have an account prior to the workshop.*

<br>

**Tools**

For this workshop, you will use Microsoft Windows as the base workstation, altough Apple and Linux operating systems can be used in production. You can <a href="https://developer.microsoft.com/en-us/windows/downloads/virtual-machines" target="_blank">download a Windows 10 Workstation Image for VirtualBox, Hyper-V, VMWare, or Parallels for free here</a>. 

*Install the SQL Server Big Data Clusters workstation tools*

- [Using this reference, install all tools on your workstation or Virtual Machine](https://docs.microsoft.com/en-us/sql/big-data-cluster/deploy-big-data-tools?view=sql-server-ver15) to use for the class. 

<p><img style="margin: 0px 15px 15px 0px;" src="../graphics/owl.png"><b>For Further Study</b></p>
<ul>
    <li><a href="https://docs.microsoft.com/en-us/sql/big-data-cluster/deploy-openshift?view=sql-server-ver15" target="_blank">Official Documentation for this section</a></li>
</ul>

<p><img style="float: left; margin: 0px 15px 15px 0px;" src="../graphics/geopin.png"><b >Next Steps</b></p>

Next, Continue to <a href="https://github.com/microsoft/sqlworkshops-bdconopenshift/blob/main/bdconopenshift/01%20-%20Introduction.md" target="_blank"><i> 01 - Module</i></a>.
