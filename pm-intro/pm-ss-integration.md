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

## Single Site - Implementation Diagrams

### Minimal Single-Site Enterprise Deployment

* Minimum Cost HA Configuration – No Shared Storage Requirement.
* RabbitMQ Installed on Secret Server Web Servers (Typically in a cluster on a primary + secondary node).
* Single Site design, no native DR capacity. DR can be provided by means of VM replication if subnets are spanning locations, otherwise re-ip + DNS changes may be necessary.
* Privilege Manager is preferably installed on separate web servers. For smaller environments, Privilege Manager can be installed on the same web servers as Secret Server and can be used for integrating authentication and can store credentials in Secret Server.
* Privilege Manager can reside on the same database servers as Secret Server or separate database servers, but Secret Server and Privilege Manager should not share the same database itself. Due to SQL Basic Availability groups with Standard Edition, you will need to have multiple instances of SQL and a separate AlwaysOn availability group configuration.
* Some customers may choose to use a separate web reverse proxy or azure service bus configuration for Privilege Manager agent TCP 443 communication.

![Minimum High Availability](images/ss-int/ss-a1.png "Minimum High Availability")

### Average Single-Site Enterprise Deployment (Reverse Proxy/Azure Bus)

* Minimum Cost HA Configuration – No Shared Storage Requirement.
* RabbitMQ Installed on separate servers.
* Single Site design, no native DR capacity. DR can be provided by means of VM replication if subnets are spanning locations, * otherwise re-ip + DNS changes may be necessary.
* Privilege Manager is preferably installed on separate web servers. For smaller environments, Privilege Manager can be installed on the same web servers as Secret Server and can be used for integrating authentication and can store credentials in Secret Server.
* Privilege Manager can reside on the same database servers as Secret Server or separate database servers, but Secret Server and Privilege Manager should not share the same database itself. Due to SQL Basic Availability groups with Standard Edition, you will need to have multiple instances of SQL and a separate AlwaysOn availability group configuration.
* Some customers may choose to use a separate web reverse proxy or azure service bus configuration for Privilege Manager agent TCP 443 communication.

![reverse-proxy](images/ss-int/ss-a2.png "Minimum High Availability (Reverse Proxy/Azure Bus)")

## Multi Site - Implementation Diagrams

### Minimum HA/DR" Enterprise Scale Deployment

* Minimum Cost HA Multi-Site Configuration – No Shared Storage Requirement.
* RabbitMQ Installed on Secret Server Web Servers (Typically in a cluster on a primary + secondary node).
* Multi-Site Design. SQL AlwaysOn configurations will be either synchronous/asynchronous for Secret Server database and asynchronous only for Privilege Manager database.
* DR site acts at temporary site only with no intention for long-term usage. Services in DR site being down can incur downtime.
* Privilege Manager is preferably installed on separate web servers. For smaller environments, Privilege Manager can be installed on the same web servers as Secret Server and can be used for integrating authentication and can store credentials in Secret Server.
* Privilege Manager can reside on the same database servers as Secret Server or separate database servers, but Secret Server and * Privilege Manager should not share the same database itself. Due to SQL Basic Availability groups with Standard Edition, you will need to have multiple instances of SQL and a separate AlwaysOn availability group configuration.
* Some customers may choose to use a separate web reverse proxy or azure service bus configuration for Privilege Manager agent TCP 443 communication.

![lowest cost](images/ss-int/ss-a3.png "Minimum High Availability (with Multi Site DR) - Lower Cost/Manual Failover")

### Average HA/DR" Enterprise Scale Deployment

* Average Cost HA Multi-Site Configuration – No Shared Storage Requirement.
* RabbitMQ Installed on separate servers.
* Multi-Site Design. SQL AlwaysOn configurations will be either synchronous/asynchronous for Secret Server database and asynchronous only for Privilege Manager database.
* DR site acts at temporary site only with no intention for long-term usage. Services in DR site being down can incur downtime.
* Privilege Manager is preferably installed on separate web servers. For smaller environments, Privilege Manager can be installed on the same web servers as Secret Server and can be used for integrating authentication and can store credentials in Secret Server.
* Privilege Manager can reside on the same database servers as Secret Server or separate database servers, but Secret Server and Privilege Manager should not share the same database itself.
* Secondary SQL Node at Primary Site for Planned Failover "Patching", Secondary SQL Node in DR Site for Unplanned Failover.
* Some customers may choose to use a separate web reverse proxy or azure service bus configuration for Privilege Manager agent TCP 443 communication.

![average cost](images/ss-int/ss-c.png "Average High Availability (with Multi Site DR) - Average Cost/Manual Failover")

### Best High Availability - Enterprise Scale Deployment

* Highest Cost HA Multi-Site Configuration – No Shared Storage Requirement.
* RabbitMQ Installed on separate servers.
* Multi-Site Design. SQL AlwaysOn configurations will be either synchronous/asynchronous for Secret Server database and asynchronous only for Privilege Manager database.
* DR site acts at temporary site only with no intention for long-term usage. Services in DR site being down can incur downtime.
* Privilege Manager is preferably installed on separate web servers. For smaller environments, Privilege Manager can be installed on the same web servers as Secret Server and can be used for integrating authentication and can store credentials in Secret Server.
* Privilege Manager can reside on the same database servers as Secret Server or separate database servers, but Secret Server and Privilege Manager should not share the same database itself.
* Secondary SQL Node at Primary Site for Planned Failover "Patching", Secondary SQL Node in DR Site for Unplanned Failover.
* Some customers may choose to use a separate web reverse proxy or azure service bus configuration for Privilege Manager agent TCP 443 communication.

![high cost](images/ss-int/ss-d1.png "Best High Availability (with Multi Site DR)")

### Best HA/DR" Enterprise Scale Deployment

* Highest Cost HA Multi-Site Configuration – No Shared Storage Requirement.
* RabbitMQ Installed on separate servers.
* Multi-Site Design. SQL AlwaysOn configurations will be either synchronous/asynchronous for Secret Server database and asynchronous only for Privilege Manager database.
* DR site acts at temporary site only with no intention for long-term usage. Services in DR site being down can incur downtime.
* Privilege Manager is preferably installed on separate web servers. For smaller environments, Privilege Manager can be installed on the same web servers as Secret Server and can be used for integrating authentication and can store credentials in Secret Server.
* Privilege Manager can reside on the same database servers as Secret Server or separate database servers, but Secret Server and Privilege Manager should not share the same database itself. 
* Secondary SQL Node at Primary Site for Planned Failover "Patching", Secondary SQL Node in DR Site for Unplanned Failover.
* DR site can act as permanent secondary site for long term use.
* Some customers may choose to use a separate web reverse proxy or azure service bus configuration for Privilege Manager agent TCP 443 communication.

![high cost](images/ss-int/ss-d2.png "Best High Availability (with Multi Site DR) - Highest Cost/Manual Failover")
