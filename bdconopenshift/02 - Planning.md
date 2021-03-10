![](../graphics/microsoftlogo.png)

# Workshop: Architecting SQL Server Big Data Cluster Solutions on Red Hat OpenShift

#### <i>A Microsoft workshop from the SQL Server team</i>

<p style="border-bottom: 1px solid lightgrey;"></p>

<img style="float: left; margin: 0px 15px 15px 0px;" src="../graphics/textbubble.png"> <h2>02 Planning</h2>

In this workshop, you'll learn how to plan, implement and operate a SQL Server Big Data Cluster on the Red Hat OpenShift platform. This module covers how to plan your layout, sizing and target location to install, configure and operate your advanced analytics system. 

In each section of this Module you'll get more references, which you should follow up on to learn more. Also watch for links within the text - click on each one to explore that topic.

<a href="https://github.com/microsoft/sqlworkshops-bdconopenshift/blob/main/bdconopenshift/00%20-%20Pre-Requisites.md" target="_blank">Make sure you check out the <b>Pre-Requisites</b> page before you start</a>. You'll need all of the items loaded there before you can proceed with the workshop.

You'll cover these topics in this Module:
<dl>

  <dt>2.1 - Plan sizing for the SQL Server Big Data Cluster platform on a Red Hat OpenShift environment as a solution<dt>
  <dt>2.2 - Select a target location for the Red Hat OpenShift environment (on-premises or in-Cloud)<dt>
</dl>

<p style="border-bottom: 1px solid lightgrey;"></p>

<h2><img style="float: left; margin: 0px 15px 15px 0px;" src="../graphics/pencil2.png">2.1 Plan a layout for the SQL Server Big Data Cluster platform on a Red Hat OpenShift environment as a solution</h2>

<br>

There are two primary planning exercises you will need to consider for a proper deployment of SQL Server Big Data Cluster on Red Hat OpenShift. The first consideration involves the SQL Server BDC, followed by the OpenShift platform you have chosen. 

<h3>SQL Server Big Data Clusters Sizing Considerations</h3>

These are the primary groups of components in a SQL Server Big Data Cluster: 

<img style="height: 400; box-shadow: 0 4px 8px 0 rgba(0, 0, 0, 0.2), 0 6px 20px 0 rgba(0, 0, 0, 0.19);" src="https://github.com/microsoft/sqlworkshops-bdc/blob/master/graphics/bdc.png?raw=true">

In the [Pre-Requisistes Module you deployed a default SQL Server BDC](https://github.com/microsoft/sqlworkshops-bdconopenshift/blob/main/bdconopenshift/00%20-%20Pre-Requisites.md) on The Red Hat OpenShift platform. The Pods you deployed, in addition to the OpenShift components, [are as follows](https://docs.microsoft.com/en-us/sql/big-data-cluster/concept-architecture-pods?view=sql-server-ver15). Open each for a description of purpose and count:

- [control-<nnnn>](https://docs.microsoft.com/en-us/sql/big-data-cluster/concept-architecture-pods?view=sql-server-ver15#control)
- [controldb-<#>](https://docs.microsoft.com/en-us/sql/big-data-cluster/concept-architecture-pods?view=sql-server-ver15#control)
- [controlwd-<nnnn>](https://docs.microsoft.com/en-us/sql/big-data-cluster/concept-architecture-pods?view=sql-server-ver15#control)
- [logsdb-<#](https://docs.microsoft.com/en-us/sql/big-data-cluster/concept-architecture-pods?view=sql-server-ver15#control)
- [logsui-<nnnn>](https://docs.microsoft.com/en-us/sql/big-data-cluster/concept-architecture-pods?view=sql-server-ver15#control)
- [metricsdb-<#>](https://docs.microsoft.com/en-us/sql/big-data-cluster/concept-architecture-pods?view=sql-server-ver15#control)
- [metricsdc-<nnnn>](https://docs.microsoft.com/en-us/sql/big-data-cluster/concept-architecture-pods?view=sql-server-ver15#control)
- [metricsui-<nnnn>](https://docs.microsoft.com/en-us/sql/big-data-cluster/concept-architecture-pods?view=sql-server-ver15#control)
- [mgmtproxy-<nnnn>](https://docs.microsoft.com/en-us/sql/big-data-cluster/concept-architecture-pods?view=sql-server-ver15#control)
- [zookeeper-<#>](https://docs.microsoft.com/en-us/sql/big-data-cluster/concept-architecture-pods?view=sql-server-ver15#control)
- [dns-<nnnn>](https://docs.microsoft.com/en-us/sql/big-data-cluster/concept-architecture-pods?view=sql-server-ver15#control)
- [master-<#n>](https://docs.microsoft.com/en-us/sql/big-data-cluster/concept-architecture-pods?view=sql-server-ver15#master-instance)
- [operator-<nnnn>](https://docs.microsoft.com/en-us/sql/big-data-cluster/concept-architecture-pods?view=sql-server-ver15#master-instance)
- [compute-<#n>-<#m>](https://docs.microsoft.com/en-us/sql/big-data-cluster/concept-architecture-pods?view=sql-server-ver15#compute-pool)
- [data-<#>-<#>](https://docs.microsoft.com/en-us/sql/big-data-cluster/concept-architecture-pods?view=sql-server-ver15#data-pool)
- [storage-<#>-<#>](https://docs.microsoft.com/en-us/sql/big-data-cluster/concept-architecture-pods?view=sql-server-ver15#storage-pool)
- [nmnode-<#>-<#>](https://docs.microsoft.com/en-us/sql/big-data-cluster/concept-architecture-pods?view=sql-server-ver15#storage-pool)
- [sparkhead-<#>](https://docs.microsoft.com/en-us/sql/big-data-cluster/concept-architecture-pods?view=sql-server-ver15#storage-pool)
- [appproxy-<#m>](https://docs.microsoft.com/en-us/sql/big-data-cluster/concept-architecture-pods?view=sql-server-ver15#application-pool)
- [gateway-<#>](https://docs.microsoft.com/en-us/sql/big-data-cluster/concept-architecture-pods?view=sql-server-ver15#gateway-service)

Each of these has sizing implications. 

>NOTE: In class, the instructor will review each of these components with you for a complete discussion. If you are taking this course self-taught, you will need to [review the Deployment Configuration file](https://docs.microsoft.com/en-us/sql/big-data-cluster/reference-deployment-config?view=sql-server-ver15) on your own for proper determination. 

<h3>Red Hat OpenShift Cluster Sizing Considerations</h3>

For this course, we are using the [Microsoft Azure Red Hat OpenShift (ARO) platform](https://docs.microsoft.com/en-us/sql/big-data-cluster/deploy-openshift?view=sql-server-ver15), so we'll focus on its environment as an example of looking at the various factors involved. For your production environment, [it is essential that you fully understand the variables it requires](https://docs.openshift.com/container-platform/4.6/welcome/index.html); you can use the following information to map to your platform's environment.

<b>Azure account limits</b>


The OpenShift Container Platform cluster uses a number of Microsoft Azure components, and the default
 Azure subscription and service limits, quotas, and constraints (https://docs.microsoft.com/en-
 us/azure/azure-subscription-service-limits) affect your ability to install OpenShift Container Platform
 clusters.

  > You must increase quota limits for your account before you install a default cluster on Azure.

The following table summarizes the Azure components whose limits can impact your ability to install and run OpenShift Container Platform clusters:

<pre>
Component    Number of     Default Azure       Description
             components    limit
             required by
             default

vCPU         34            20 per region       A default cluster requires 34 vCPUs, so you must increase
                                               the account limit.

                                               By default, each cluster creates the following instances:

                                                      One bootstrap machine, which is removed after
                                                      installation

                                                      Three control plane machines

                                                      Three compute machines

                                               Because the bootstrap machine uses Standard_D4s_v3
                                               machines, which use 4 vCPUS, the control plane machines
                                               use Standard_D8s_v3 virtual machines, which use 8 vCPUs,
                                               and the worker machines use Standard_D2s_v3 virtual
                                               machines, which use 2 vCPUs, a default cluster requires 34
                                               vCPUs.

                                               To deploy more worker nodes, enable autoscaling, deploy
                                               large workloads, or use a different instance type, you must
                                               further increase the vCPU limit for your account to ensure
                                               that your cluster can deploy the machines that you require.

                                               By default, the installation program distributes control plane
                                               and compute machines across all availability zones
                                               (https://azure.microsoft.com/en-us/global-
                                               infrastructure/availability-zones/) within a region
                                               (https://azure.microsoft.com/en-us/global-
                                               infrastructure/regions). To ensure high availability for your
                                               cluster, select a region with at least three availablity zones. If
                                               your region contains fewer than three availability zones, the
                                               installation program places more than one control plane
                                               machine in the available zones.


VNet         1             1000 per region     Each default cluster requires one Virtual Network (VNet),
                                               which contains two subnets.


Network      6             65,536 per region   Each default cluster requires six network interfaces. If you
interfaces                                     create more machines or your deployed workloads create
                                               load balancers, your cluster uses more network interfaces.
Component      Number of     Default Azure     Description
               components    limit
               required by
               default

Network        2             5000              Each default cluster Each cluster creates network security
security                                       groups for each subnet in the VNet. The default cluster
groups                                         creates network security groups for the control plane and
                                               for the compute node subnets:


                                                controlplane           Allows the control plane machines to
                                                                       be reached on port 6443 from
                                                                       anywhere

                                                node                   Allows worker nodes to be reached
                                                                       from the internet on ports 80 and
                                                                       443



Network load   3             1000 per region   Each cluster creates the following load balancers
balancers                                      (https://docs.microsoft.com/en-us/azure/load-
                                               balancer/load-balancer-overview):


                                                default        Public IP address that load balances
                                                               requests to ports 80 and 443 across
                                                               worker machines

                                                internal       Private IP address that load balances
                                                               requests to ports 6443 and 22623 across
                                                               control plane machines

                                                external       Public IP address that load balances
                                                               requests to port 6443 across control plane
                                                               machines


                                               If your applications create more Kubernetes LoadBalancer
                                               Service objects, your cluster uses more load balancers.


Public IP      3                               Each of the two public load balancers uses a public IP
addresses                                      address. The bootstrap machine also uses a public IP
                                               address so that you can SSH into the machine to
                                               troubleshoot issues during installation. The IP address for
                                               the bootstrap node is used only during installation.


Private IP     7                               The internal loadbalancer, each of the three control plane
addresses                                      machines, and each of the three worker machines each use
                                               a private IP address.
</pre>


<b>Security Considerations</b>

There are also security considerations for running SQL Server Big Data Clusters on OpenShift which might affect the size of the cluster you build. For detailed YAML settings, [see this article](https://docs.microsoft.com/en-us/sql/big-data-cluster/quickstart-big-data-cluster-deploy-aro?view=sql-server-ver15#bdc-sccyaml).

<br>

<p><img style="float: left; margin: 0px 15px 15px 0px;" src="../graphics/point1.png"><b>Activity: Review Configuration File</b></p>

In this Activity you will review the pre-requisites you need to install the Big Data Cluster system on Red Hat OpenShift. If you are taking this Workshop in a group environment, you will review these scripts with the instructor. If you are taking this Workshop on your own, ensure you understand each step in the script and configuration; search for any terms or files you are not familiar with. 

<p><img style="margin: 0px 15px 15px 0px;" src="../graphics/checkmark.png"><b>Dumping the Configuration File</b></p>

 - Open the following [reference and review the information and video you see there.](https://docs.microsoft.com/en-us/sql/big-data-cluster/deploy-big-data-tools?view=sql-server-ver15)

<p style="border-bottom: 1px solid lightgrey;"></p>

<h2><img style="float: left; margin: 0px 15px 15px 0px;" src="../graphics/pencil2.png">2.2 - Select a target location for the Red Hat OpenShift environment (on-premises or in-Cloud)</h2>

<br>

There are various decision-points for choosing your platform location. In general you can start with data movement: if you are generating most of your data on-premises and also serving it to internal clients, that may be a strong justification for locating the system on-premesis. Also, regulatory requirements may enforce a local choice. Purchasing equipment, providing factilities, and staffing comprise the major costs in this approach. On-premises systems provide complete control over all aspects of the deployment, but require more responsibility.

Using a Cloud provider such as Microsoft or Red Hat has the advantage of handling the infrastructure, deployments, monitoring and other factors. Staffing and facilities costs are reduced, but control over the hardware and networking equipment are ceded to the provider. Costs in this scenario are variable, since you can expand the hardware and systems involved dynamically. 

> Note that you can have a hybrid approach, with data flowing both directions to and from a given architecture, however it is not advised to stretch Nodes or Pods from on-premises to cloud due to network transmission loads.

Creating a Decision Chart is the best way to show your requirements and constraints for your choices. [You can find an example of this process here](https://www.mindtools.com/pages/article/newTED_03.htm#:~:text=How%20to%20Use%20the%20Tool.%201%20Step%201.,3.%204%20Step%204.%205%20Step%205.).

<br>

<p><img style="float: left; margin: 0px 15px 15px 0px;" src="../graphics/point1.png"><b>Activity: <TODO: Determine Topic Activity</b></p>

In this Activity you will review the installation you performed during the pre-requisites section. If you are taking this Workshop in a group environment, you will review these scripts with the instructor. If you are taking this Workshop on your own, ensure you understand each step in the script and configuration; search for any terms or files you are not familiar with. 

<p><img style="margin: 0px 15px 15px 0px;" src="../graphics/checkmark.png"><b><TODO: Step Name</b></p>

 - Create a decision matrix for an on-premises OpenShift cluster running SQL Server Big Data Cluster
 - Create a decision matrix for an in-cloud OpenShift cluster running SQL Server Big Data Cluster
  

<p style="border-bottom: 1px solid lightgrey;"></p>

<p><img style="margin: 0px 15px 15px 0px;" src="../graphics/owl.png"><b>For Further Study</b></p>
<ul>
    <li><a href="https://docs.openshift.com/container-platform/4.6/welcome/index.html " target="_blank">Red Hat OpenShift Documentation on Planning</a></li>
</ul>


Next, Continue to <a href="https://github.com/microsoft/sqlworkshops-bdconopenshift/blob/main/bdconopenshift/03%20-%20Deployment.md" target="_blank"><i> 03 Deployment</i></a>.

