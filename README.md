![](graphics/microsoftlogo.png)

# Workshop: Architecting SQL Server Big Data Cluster Solutions on Red Hat OpenShift

#### <i>A Microsoft Course from the SQL Server team</i>

<p style="border-bottom: 1px solid lightgrey;"></p>

<img style="float: left; margin: 0px 15px 15px 0px;" src="https://raw.githubusercontent.com/microsoft/sqlworkshops/master/graphics/textbubble.png"> <h2>About this Workshop</h2>

Welcome to this Microsoft solutions workshop on *Architecting SQL Server Big Data Cluster Solutions on Red Hat OpenShift*. In this workshop, you'll learn how to plan, implement and operate a SQL Server Big Data Cluster on the Red Hat OpenShift platform. 

This workshop focuses on the **Architect** role (*the person or team tasked with planning, designing and implementing the system*). This course sets the groundwork for the **Operator** role (*those who manage, monitor and secure the system*) and the **Developer** role (*those who create applications and background services for the system*). This course is designed as a "Delta" course explaining the differences of planning, installing and operating a SQL Server Big Data Cluster on a Red Hat OpenShift cluster. 

> **NOTE:** You should be familiar with Linux, Containers, Kubernetes, Red Hat OpenShift, and SQL Server Big Data Clusters prior to taking this course. Resources are provided below if you are new to these technologies. 

You'll start with a quick review of your understanding of Virtualization and the Kubernetes Orchestration system, and how SQL Server Big Data Clusters is implemented on this environment. You'll also review the key concepts of the Red Hat OpenShift platform. This rest of the course focuses on learning now the SQL Server Big Data Cluster system works on the Red Hat OpenShift Platform, whether on-premises on in a Cloud environment.

This [github README.MD file](https://lab.github.com/githubtraining/introduction-to-github) explains how the workshop is laid out, what you will learn, and the technologies you will use in this solution. To download this Lab to your local computer, click the **Clone or Download** button you see at the top right side of this page. [More about that process is here](https://help.github.com/en/github/creating-cloning-and-archiving-repositories/cloning-a-repository). 

You can view all of the [courses and other workshops our team has created at this link - open in a new tab to find out more.](https://microsoft.github.io/sqlworkshops/)

<p style="border-bottom: 1px solid lightgrey;"></p>

<img style="float: left; margin: 0px 15px 15px 0px;" src="https://raw.githubusercontent.com/microsoft/sqlworkshops/master/graphics/checkmark.png"> <h3>Learning Objectives</h3>

In this workshop you'll learn how to:
<br>

- Plan a layout for the SQL Server Big Data Cluster platform on a Red Hat OpenShift environment as a solution
- Plan a sizing strategy for the solution
- Select a target location for the Red Hat OpenShift environment (onp-premises or in-Cloud)
- Implement the proper licensing for the solution
- Deploy a SQL Server Big Data Cluster to Red Hat OpenShift
- Leverage the Endpoints and Interfaces for the solution
- Implement a security strategy for the solution
- Manage the solution using built-in tools for each component, and comprehensive monitoring with Grafana and Kibana

<p style="border-bottom: 1px solid lightgrey;"></p>

<img style="float: left; margin: 0px 15px 15px 0px;" src="https://raw.githubusercontent.com/microsoft/sqlworkshops/master/graphics/owl.png"> <h2>Before Taking this Workshop</h2>

 - You'll need a local system that you are able to install software on. The workshop demonstrations use Microsoft Windows as an operating system and all examples use Windows for the workshop. Optionally, you can use a Microsoft Azure Virtual Machine (VM) to install the software on and work with the solution.
- You must have a Microsoft Azure account with the ability to create assets.

This workshop expects that you understand Linux, Virtualization, the Kubernetes Orchestration system, SQL Server Big Data Clusters and Red Hat OpenShift platform. If you are new to these technologies, there are a  few references you can complete prior to taking the course:

 <table style="tr:nth-child(even) {background-color: #f2f2f2;}; text-align: left; display: table; border-collapse: collapse; border-spacing: 2px; border-color: gray;">

  <tr><th style="background-color: #1b20a1; color: white;">Technology</th> <th style="background-color: #1b20a1; color: white;">Description</th></tr>

  <tr><td>Linux</td><td><a href="https://www.digitalocean.com/community/tutorial_series/getting-started-with-linux" target="_blank">Online course from Community Tutorials</a></td></tr>
  <tr><td>Containers</td><td><a href="https://docker-curriculum.com/" target="_blank">Online course from Docker</a></td></tr>
  <tr><td>Kubernetes</td><td><a href="https://www.katacoda.com/courses/kubernetes" target="_blank">Online course with free online environment from Katacoda</a></td></tr>
  <tr><td>Red Hat OpenShift Platform</td><td><a href="https://learn.openshift.com/" target="_blank">Online course from Red Hat with free online environment</a></td></tr>
  <tr><td>Microsoft SQL Server</td><td><a href="https://www.microsoft.com/en-us/learning/sql-training.aspx" target="_blank">Multiple training options from Microsoft</a></td></tr>
  <tr><td>Microsoft SQL Server Big Data Clusters</td><td><a href="https://github.com/Microsoft/sqlworkshops-bdc" target="_blank">Online workshop from Microsoft</a></td></tr>

</table>

<img style="float: left; margin: 0px 15px 15px 0px;" src="https://raw.githubusercontent.com/microsoft/sqlworkshops/master/graphics/bulletlist.png"> <h3>Setup</h3>

<a href="url" target="_blank">A full pre-requisites document is located here</a>. These instructions should be completed before the workshop starts, since you will not have time to cover these in class. <i>Remember to turn off any Virtual Machines from the Azure Portal when not taking the class so that you do incur charges (shutting down the machine in the VM itself is not sufficient)</i>.

<p style="border-bottom: 1px solid lightgrey;"></p>

<img style="float: left; margin: 0px 15px 15px 0px;" src="https://raw.githubusercontent.com/microsoft/sqlworkshops/master/graphics/education1.png"> <h2>Workshop Details</h2>

This workshop uses <TODO: enter main technologies used to solve the sceanrio>, with a focus on <TODO: architecture and implementation, development and use, etc>.

<table style="tr:nth-child(even) {background-color: #f2f2f2;}; text-align: left; display: table; border-collapse: collapse; border-spacing: 5px; border-color: gray;">

  <tr><td style="background-color: Cornsilk; color: black; padding: 5px 5px;">Primary Audience:</td><td style="background-color: Cornsilk; color: black; padding: 5px 5px;">TODO: Enter the technical people who will take the workshop> tasked with TODO: Enter what they are tasked to do</td></tr>
  <tr><td>Secondary Audience:</td><td> TODO: Secondary Audience</td></tr>
  <tr><td style="background-color: Cornsilk; color: black; padding: 5px 5px;">Level: </td><td style="background-color: Cornsilk; color: black; padding: 5px 5px0;"> TODO: 100, 200, 300, 400 </td></tr>
  <tr><td>Type:</td><td>TODO: In-Person, On-Line, or from github</td></tr>
  <tr><td style="background-color: Cornsilk; color: black; padding: 5px 5px;">Length: </td><td style="background-color: Cornsilk; color: black; padding: 5px 5px;">TODO: Number of hours</td></tr>

</table>

<p style="border-bottom: 1px solid lightgrey;"></p>

<img style="float: left; margin: 0px 15px 15px 0px;" src="https://raw.githubusercontent.com/microsoft/sqlworkshops/master/graphics/pinmap.png"> <h2>Related Workshops</h2>

 - [TODO: Enter any other workshops that help in this area](url)

<p style="border-bottom: 1px solid lightgrey;"></p>

<img style="float: left; margin: 0px 15px 15px 0px;" src="https://raw.githubusercontent.com/microsoft/sqlworkshops/master/graphics/bookpencil.png"> <h2>Workshop Modules</h2>

This is a modular workshop, and in each section, you'll learn concepts, technologies and processes to help you complete the solution.

<table style="tr:nth-child(even) {background-color: #f2f2f2;}; text-align: left; display: table; border-collapse: collapse; border-spacing: 5px; border-color: gray;">

  <tr><td style="background-color: AliceBlue; color: black;"><b>Module</b></td><td style="background-color: AliceBlue; color: black;"><b>Topics</b></td></tr>

  <tr><td><a href="url" target="_blank">TODO: 01 - Module Name </a></td><td> TODO: Module Description</td></tr>
  <tr><td style="background-color: AliceBlue; color: black;"><a href="url" target="_blank">TODO: 02 - Module 2</a> </td><td td style="background-color: AliceBlue; color: black;"> TODO: Module Description</td></tr>
  <tr><td><a href="url" target="_blank">TODO: 03 - Module Name </a></td><td> TODO: Module Description</td></tr>
  <tr><td style="background-color: AliceBlue; color: black;"><a href="url" target="_blank">TODO: 04 - Module 2</a> </td><td td style="background-color: AliceBlue; color: black;"> TODO: Module Description</td></tr>  <tr><td><a href="url" target="_blank">TODO: 05 - Module Name </a></td><td> TODO: Module Description</td></tr>
  <tr><td style="background-color: AliceBlue; color: black;"><a href="url" target="_blank">TODO: 06 - Module 2</a> </td><td td style="background-color: AliceBlue; color: black;"> TODO: Module Description</td></tr>

</table>

<p style="border-bottom: 1px solid lightgrey;"></p>

<p><img style="float: left; margin: 0px 15px 15px 0px;" src="https://raw.githubusercontent.com/microsoft/sqlworkshops/master/graphics/geopin.png"><b>Next Steps</b></p>

Next, Continue to <a href="url" target="_blank"><i> Pre-Requisites</i></a>

# Contributing

This project welcomes contributions and suggestions.  Most contributions require you to agree to a
Contributor License Agreement (CLA) declaring that you have the right to, and actually do, grant us
the rights to use your contribution. For details, visit https://cla.opensource.microsoft.com.

When you submit a pull request, a CLA bot will automatically determine whether you need to provide
a CLA and decorate the PR appropriately (e.g., status check, comment). Simply follow the instructions
provided by the bot. You will only need to do this once across all repos using our CLA.

This project has adopted the [Microsoft Open Source Code of Conduct](https://opensource.microsoft.com/codeofconduct/).
For more information see the [Code of Conduct FAQ](https://opensource.microsoft.com/codeofconduct/faq/) or
contact [opencode@microsoft.com](mailto:opencode@microsoft.com) with any additional questions or comments.

# Legal Notices

### License
Microsoft and any contributors grant you a license to the Microsoft documentation and other content in this repository under the [Creative Commons Attribution 4.0 International Public License](https://creativecommons.org/licenses/by/4.0/legalcode), see [the LICENSE file](https://github.com/MicrosoftDocs/mslearn-tailspin-spacegame-web/blob/master/LICENSE), and grant you a license to any code in the repository under [the MIT License](https://opensource.org/licenses/MIT), see the [LICENSE-CODE file](https://github.com/MicrosoftDocs/mslearn-tailspin-spacegame-web/blob/master/LICENSE-CODE).

Microsoft, Windows, Microsoft Azure and/or other Microsoft products and services referenced in the documentation
may be either trademarks or registered trademarks of Microsoft in the United States and/or other countries.
The licenses for this project do not grant you rights to use any Microsoft names, logos, or trademarks.
Microsoft's general trademark guidelines can be found at http://go.microsoft.com/fwlink/?LinkID=254653.

Privacy information can be found at https://privacy.microsoft.com/en-us/

Microsoft and any contributors reserve all other rights, whether under their respective copyrights, patents,
or trademarks, whether by implication, estoppel or otherwise.