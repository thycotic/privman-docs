[title]: # (Integration with Secret Server)
[tags]: # (setup planning)
[priority]: # (20)
# Integration with Secret Server

Privilege Manager and Secret Server integration is supported in a co-hosted setting when installed on the same server or on separate servers. If integrated on separate servers, Privilege Manager communicates with Secret Server via Secret Server's REST API. 

The benefits of Privilege Manager's integration with Secret Server include:

* Secret Server can be the authentication source for Privilege Manager, which:

  * Adds Secret Server's MFA login options to Privilege Manager logins.
  * Gives one place for role assignments for both products.

* Allows Privilege Manager to use Secret Server as a storage container. If Secret Server is used as a storage container for Privilege Manager credentials, Privilege Manager

  * creates Secrets for each local credential managed by Privilege Manager.
  * creates Secrets for each Configuration Credential stored in Privilege Manager. This includes credentials used for Foreign Systems, such as AD Sync, ServiceNow, etc.
  * does not pull any changes for these Secrets. Privilege Manager only stores the credentials in Secret Server to utilize Secret Server's workflow options for other users to view.

When Secret Server is used as the authentication source for Privilege Manager, Role Permissions assigned in Secret Server are important and determine user access levels in Privilege Manager. Without Secret Server integration, Privilege Manager uses NTLM for WebServer and Azure AD as possible authentication sources.

## Component Definition

__App User__ - These are the users connecting to your Privilege Manager websites. These users will be limited to the users that perform administrative tasks (admins), to use the solution in a helpdesk role, or to perform approvals or audits.

__Privilege Manager Agents__ - These is used for application control and local user/group management.

__Load Balancers__ - Load balancers are often involved in the solution to help distribute web traffic to more than one web server. Local and Global load balancers, if available, may be used in the solution to further lower potential application downtime during upgrades, patching, and single site failures.

__Web Server__ - This is a primary component of the solution. Our web servers use IIS 7 and newer and will only work on Windows Server 2008 R2 - Windows Server 2016. For multiple web server (clustered) solutions, the web application itself can be made cluster aware and does not require being built as part of an IIS farm. Each web server acts as its own stand alone web server.

__Database Server__ - This is a primary component of the solution. Microsoft SQL Server hosts the Privilege Manager databases. We are compatible only with SQL Server 2012 or newer running on Windows Server 2008 R2 - Windows Server 2016. The Thycotic databases can be put on a stand alone server, a FCI, or preferably using an AlwaysOn AG for clustered environments. The databases can be added to an existing production SQL cluster or instance, but proper sizing of the environment should be done. Windows authentication only is advised.

__Reverse Proxy / Azure Service Bus__ - A properly configured Reverse Proxy will act as a buffer between Privilege Manager agents and the Privilege Manager server(s) to limit server exposure. Use nginx, F5, or Windows Application Request Routing 3.0 and URL Rewrite in IIS on a DMZ Server, to prevent a direct connection between Agent endpoints and your Privilege Manager web server(s). Alternatively, Azure Bus can be used, to prevent Agent endpoints connecting directly to your Privilege Manager web server(s).

__Secret Server__ - Optionally, Secret Server can be installed with Privilege Manager to use an authentication source and a storage vault for Privilege Manager credentials. Using Secret Server as the authentication source for Privilege Manager allows MFA options for login. Also, application role assignment can be assigned in Secret Server. If using Secret Server features (beyond authentication and vault storage for Privilege Manager), Secret Server should be on separate servers - for this, see separate Secret Server + Privilege Manager Architectures. 

>**Note**:
>Every component of Privilege Manager can be made highly available to ensure a redundant architecture and to scale for future growth.

## Single Site - Implementation Diagrams

### Minimum High Availability

![Minimum High Availability](images/ss-int/a1.png "Minimum High Availability")

### Minimum High Availability (Reverse Proxy/Azure Bus)

![reverse-proxy](images/ss-int/a2.png "Minimum High Availability (Reverse Proxy/Azure Bus)")

## Multi Site - Implementation Diagrams

### Minimum High Availability (with Multi Site DR) - Lower Cost/Manual Failover

![lowest cost](images/ss-int/b1.png "Minimum High Availability (with Multi Site DR) - Lower Cost/Manual Failover")

### Average High Availability (with Multi Site DR) - Average Cost/Manual Failover

![average cost](images/ss-int/c.png "Average High Availability (with Multi Site DR) - Average Cost/Manual Failover")

### Best High Availability (with Multi Site DR) - Highest Cost/Manual Failover

![high cost](images/ss-int/d1.png "Best High Availability (with Multi Site DR) - Highest Cost/Manual Failover")
