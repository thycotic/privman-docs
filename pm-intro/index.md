[title]: # (Product Overview)
[tags]: # (architecture)
[priority]: # (11)
# Product Overview

The following diagrams provide an architectural overview of Privilege Manager, its components, and available integrations.

## Privilege Manager Cloud - Layered Diagram

![PM Implementation Overview](images/privman-arch-20190415.png "Cloud Layered Diagram")

<!--
### Network Diagram (Cloud)

![PM Cloud Architecture](images/privman-cloud.png "Cloud Diagram")
-->
## Privilege Manager On-premises - Layered Diagram

![PM Implementation Overview](images/privman-arch-on-prem-20190415.png "On-prem Layered Diagram")
<!--
### Network Diagram (On-prem)

![PM On-Premises Architecture](images/privman-on-prem.png "On-prem Diagram")
-->

## Reference Diagrams

### Component Definition

__App User__ - These are the users connecting to your Privilege Manager websites. These users will be limited to the users that perform administrative tasks (admins), to use the solution in a helpdesk role, or to perform approvals or audits.

__Privilege Manager Agents__ - These is used for application control and local user/group management.

__Load Balancers__ - Load balancers are often involved in the solution to help distribute web traffic to more than one web server. Local and Global load balancers, if available, may be used in the solution to further lower potential application downtime during upgrades, patching, and single site failures.

__Web Server__ - This is a primary component of the solution. Our web servers use IIS 7 and newer and will only work on Windows Server 2008 R2 - Windows Server 2016. For multiple web server (clustered) solutions, the web application itself can be made cluster aware and does not require being built as part of an IIS farm. Each web server acts as its own stand alone web server.

__Database Server__ - This is a primary component of the solution. Microsoft SQL Server hosts the Privilege Manager databases. We are compatible only with SQL Server 2012 or newer running on Windows Server 2008 R2 - Windows Server 2016. The Thycotic databases can be put on a stand alone server, a FCI, or preferably using an AlwaysOn AG for clustered environments. The databases can be added to an existing production SQL cluster or instance, but proper sizing of the environment should be done. Windows authentication only is advised.

__Reverse Proxy / Azure Service Bus__ - A properly configured Reverse Proxy will act as a buffer between Privilege Manager agents and the Privilege Manager server(s) to limit server exposure. Use nginx, F5, or Windows Application Request Routing 3.0 and URL Rewrite in IIS on a DMZ Server, to prevent a direct connection between Agent endpoints and your Privilege Manager web server(s). Alternatively, Azure Bus can be used, to prevent Agent endpoints connecting directly to your Privilege Manager web server(s).

__Secret Server__ - Optionally, Secret Server can be installed with Privilege Manager to use an authentication source and a storage vault for Privilege Manager credentials. Using Secret Server as the authentication source for Privilege Manager allows MFA options for login. Also, application role assignment can be assigned in Secret Server. If using Secret Server features (beyond authentication and vault storage for Privilege Manager), Secret Server should be on separate servers - for this, see [Secret Server + Privilege Manager Architectures](pm-ss-integration.md).

>**Note**:
>Every component of Privilege Manager can be made highly available to ensure a redundant architecture and to scale for future growth.

### Single Site - Implementation Diagrams

#### Minimum High Availability

![Minimum High Availability](images/ss-int/a1.png "Minimum High Availability")

#### Minimum High Availability (Reverse Proxy/Azure Bus)

![reverse-proxy](images/ss-int/a2.png "Minimum High Availability (Reverse Proxy/Azure Bus)")

### Multi Site - Implementation Diagrams

#### Minimum High Availability (with Multi Site DR) - Lower Cost/Manual Failover

![lowest cost](images/ss-int/b1.png "Minimum High Availability (with Multi Site DR) - Lower Cost/Manual Failover")

#### Average High Availability (with Multi Site DR) - Average Cost/Manual Failover

![average cost](images/ss-int/c.png "Average High Availability (with Multi Site DR) - Average Cost/Manual Failover")

#### Best High Availability (with Multi Site DR) - Highest Cost/Manual Failover

![high cost](images/ss-int/d1.png "Best High Availability (with Multi Site DR) - Highest Cost/Manual Failover")
