[title]: # (Privilege Manager System Requirements)
[tags]: # (System Requirements,Ports)
[priority]: # (201)
# Privilege Manager System Requirements

## Minimum Requirements

| Web Server | Database Server |
| ----- | ----- |
| 4 CPU Cores | 4 CPU Cores |
| 8 GB RAM | 16 GB RAM |
| 40 GB Disk Space | 150 GB Disk Space |
| Windows Server 2008 R2 SP1 or newer | Windows Server 2008 R2 SP1 or newer |
| IIS 7 or newer | SQL Server 2012 or newer |
| .NET 4.6.1 or newer |  |
| Powershell 3.0 or newer |   |

## Recommended Requirements

>[!Note]
>Environments with over 25,000 Endpoints require a scoping call with a Thycotic engineer.

| Web Server | Database Server |
| ----- | ----- |
| 8 CPU Cores | 8 CPU Cores |
| 32 GB RAM | 64 GB RAM |
| 40 GB Disk Space | 500 GB Disk Space |
| Windows Server 2012 or newer | Windows Server 2012 or newer |
| IIS 7 or newer | SQL Server 2012 or newer |
| .NET 4.6.1 or newer | |  
| Powershell 5.0 or newer | |  

## Client Requirements

* RAM, CPU, and Disk Space - negligible
* Windows XP SP 3 or newer (See a complete list of Windows OS versions here)
  Thycotic performs validation on the latest Windows OS that is available via the Microsoft Insider Program to ensure any required changes are made prior to a new OS version release.
* MacOS 10.11 (El Capitan) or newer (See a complete list of Mac OS versions here)

## Details

* System Requirements apply to both physical and virtual machines
* For best performance, we recommend using dedicated (clean) servers for Thycotic products
* PowerShell must be allowed to execute and cannot be blocked on the server or the endpoint by other products
* If .NET and/or IIS features are not already installed on the web server, the Thycotic Installer will add and configure them automatically
* If SQL is not already installed on a database server, the Thycotic Installer can setup SQL Express on the web server, however SQL Express is intended for Trials and Sandbox environments ONLY. Though Thycotic will support SQL Express, users will likely experience performance issues due to the memory and product limitations. If experiencing performance issues while using SQL Express, it is highly recommended to upgrade to SQL Server prior to contacting Thycotic Support.
* A link to Microsoft documentation on the use and limitations of SQL Express can be found at: https://docs.microsoft.com/en-us/sql/sql-server/editions-and-components-of-sql-server-2017
* Web Servers that are NOT supported: Small Business Server (SBS), The Essentials Edition, Domain Controllers, Sharepoint Servers

## Ports/Agent Access Information

* Outbound (port 443 - HTTPS): This is the default access port through which the agent connects to the server. You may specify a different port based on your environment.
* Inbound (port 5593): The is the default and only port that the agent listens on. This port is not required and you can block port 5593. If you block the port, the agents pull updates from the server based on a set schedule.
* SQL (port 1433): This is the default SQL DB port. The SQL port can be customized.