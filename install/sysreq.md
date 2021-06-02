[title]: # (System Requirements)
[tags]: # (ports,on-premises)
[priority]: # (1501)
# Privilege Manager System Requirements

These are requirement for an on-premises integration.

>**Note**: Verify that the .NET version between the Privilege Manager and Database Server in use are matching, especially if installed on different Windows Server versions.

## Minimum Requirements

| Web Server | Database Server |
| ----- | ----- |
| 4 CPU Cores | 4 CPU Cores |
| 8 GB RAM | 16 GB RAM |
| 40 GB Disk Space | 150 GB Disk Space |
| Windows Server 2012 R2 or newer | Windows Server 2012 R2 or newer |
| IIS 7 or newer | SQL Server 2012 or newer |
| .NET 4.6.1 or newer |  |
| Powershell 3.0 or newer |   |

## Recommended Requirements

>**Note**:
>Environments with over 25,000 Endpoints require a scoping call with a Thycotic engineer.

| Web Server | Database Server |
| ----- | ----- |
| 8 CPU Cores | 8 CPU Cores |
| 32 GB RAM | 64 GB RAM |
| 40 GB Disk Space | 500 GB Disk Space |
| Windows Server 2016 or newer | Windows Server 2016 or newer |
| IIS 7 or newer | SQL Server 2012 or newer |
| .NET 4.6.1 or newer | |  
| Powershell 5.0 or newer | |  

## Client Requirements

For details refer to the Agent specific system requirements as provided under these topics:

* [macOS Endpoint System Requirements](agents/macOS/index.md#macos_agent_system_requirements)
* [Unix/Linux Endpoint System Requirements](agents/nix/index.md#unix_linux_agent_system_requirements)
* [Windows Endpoint System Requirements](agents/win/index.md#installing_windows_agents)
* RAM, CPU, and Disk Space - negligible

## Details

* System Requirements apply to both physical and virtual machines.
* For best performance, we recommend using dedicated (clean) servers for Thycotic products.
* PowerShell must be allowed to execute and cannot be blocked on the server or the endpoint by other products.
* If .NET and/or IIS features are not already installed on the web server, the Thycotic Installer will add and configure them automatically.
* If SQL is not already installed on a database server, the Thycotic Installer can setup SQL Express on the web server, however SQL Express is intended for Trials and Sandbox environments ONLY. Though Thycotic will support SQL Express, users will likely experience performance issues due to the memory and product limitations. If experiencing performance issues while using SQL Express, it is highly recommended to upgrade to SQL Server prior to contacting Thycotic Support.
* A link to Microsoft documentation on the use and limitations of SQL Express can be found at: https://docs.microsoft.com/en-us/sql/sql-server/editions-and-components-of-sql-server-2017
* Web Servers that are NOT supported: Small Business Server (SBS), The Essentials Edition, Domain Controllers, Sharepoint Servers.

## Ports/Agent Access Information

* __Outbound (port 443 - HTTPS)__: This is the default access port through which the agent connects to the server. You may specify a different port based on your environment.
* __Inbound (port 5593)__: The is the default and only port that the agent listens on. This port is not required and you can block port 5593. If you block the port, the agents pull updates from the server based on a set schedule.
* __SQL (port 1433)__: This is the default SQL DB port. The SQL port can be customized.
