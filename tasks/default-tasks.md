[title]: # (Tasks Overview)
[tags]: # (default)
[priority]: # (6001)
# Tasks Overview

Tasks are set-up via __Admin | More__ and then selecting the Tasks link. They are categorized by the following folders:

* Client Tasks
* HelpDesk Tasks
* Infrastructure Scheduled Activities
* Server Tasks

## Client Tasks

Client Tasks are used to run or schedule activities at the endpoints, like:

* Basic Inventory, which triggers the agent to immediately report basic inventory back to the server. The information can be viewed for a computer under Known Data. Data sets are different based on endpoint operating system.
* Resource Discovery Client Task, which populates agent-side data for any resources that have been discovered but lack detailed information.
* Update Applicable Policies, which triggers policy updates at the endpoints.

## HelpDesk Tasks

By default this folder is empty. Administrators can use it to copy tasks for HelpDesk users to run them. The HelpDesk folder provides security settings on those folders that would grant permissions if someone puts tasks in that area.
<!-- follow up -->

## Infrastructure Scheduled Activities

These are tasks that pertain to either core functions  or to components and subcomponents of Privilege Manager.

| Component | Task | Description |
| ----- | ----- | ----- |
| Core, no folder at root level | Client Items Update | Updates client items required by agents. |
| | Collection and Resource Targeting Update | Updates collections and resource targets. |
| | Collection Update | Update collections. |
| | Import Local Group Policy Definitions | Loads Group Policy Definitions from the local machine. |
| | Import Secret Server Licenses | A scheduled import of licenses from Secret Server. |
| | Licensing Update | Updates licensing product counts. |
| | Resource Discovery | Run this task to populate data for resources that have been discovered but lack detailed information. |
| | Resource Target Update | Use this task to updates resource targeting. |
| Application Control | | |
| App Control Cylance | Refresh Cylance Security Rating Report| Refreshes Cylance security rating reports on a schedule. |
| App Control VirusTotal | Recalculate Ratings for VirusTotal Provider | Recalculates security rating levels for resource rated by the given provider. |
| | Refresh VirusTotal Security Rating Reports | Refreshes VirusTotal security rating reports on a schedule. |
| Approval | ServiceNow Approval | Initiates a ServiceNow approval process and waits for the result. |
| Configuration | Reconfigure for System Secret Vault Change | This task is run by the system when the configured system secret vault setting has changed. |
| Data Feed | Content Tasks | Download Data Feed Entry - Download Data Feed Entity. |
| | | Import Data Feed Entry - Imports data feed entities and their corresponding data feeds, primarily designed to be used by the Setup component. |
| | | Import Product Configuration Package - Download Data Feed Entity. |
| | Update Tasks | Clear Data Feed Entity Updated - Clear Data Feed Entity.|
| | | Update Data Feed - Updates the Privilege Manager Configuration Feed List|
| | | Update TMS Configuration List Data Feed - Updates the Privilege Manager Configuration Feed List. |
| Directory Services | Active Directory Merge Computers | Merges computers created by Directory Services. |
| | Active Directory Merge Single Computer | Merges a single computer during agent registration. Needed if AD Sync has occurred before agent registration. |
| | Import Secret Server Domains | A scheduled import of AD domains from Secret Server. |
| | OU Directory Scope Collection Update | This task updates the membership of Directory Services OU scope collections. |
| | Promote Windows Domains | Promotes any Windows domains to Active Directory domains. |
| | Update Active Directory Details | Updates Active directory domain details including domain controllers. |
| File Inventory | Update File Filter Security Catalogs | Updates security catalogs associated with File Collection Security Catalog Filter items. |
| Import Activities | Import Packages | Imports multiple product packages, data feed entries and performs initial configuration, primarily designed to be used by the Setup component. |
| | Import Packages v3 | Imports multiple product packages, data feed entries and performs initial configuration, primarily designed to be used by the Setup component. |
| | Install Products V4 | This task installs product NuGet packages. |
| | Install Products V4 (Server Nodes) | This task is used to upgrade binaries for additional server nodes. |
| | Install Products V5 | This task installs product NuGet packages. |
| | Install Products V5 (Server Nodes) | This task is used to upgrade binaries for additional server nodes. |
| Local Security | Primary User Update | Updates the primary user for each computer in the given collection. |
| | User Credentials Data Update | This task ensures that resource credentials match the source user data. |
| Maintenance Tasks | Assign Orphaned Agent Uploads | This task assigns agent event uploads that have been orphaned. |
| | Clear Client Item Cache | This server task clears entries from the Client Item Cache that are older than the time period specified. |
| | Delete Old Performance Counter Events | This task deletes internal performance counter events last updated before the specified time. |
| | Purge Maintenance - Agent Logs | This server task removes all Agent Log data that is older than the time period specified. |
| | Purge Maintenance - Application Control Events | Purges the selected Application Control Event types from the database based on the time range specified. |
| | Purge Maintenance - Audit Events | This task removes audit event records older than the specified time period. |
| | Purge Maintenance - Completed File Upload Sessions | This task removes completed file upload sessions older than the specified time period.|
| | Purge Maintenance - Files Undiscovered | Run this task to delete file resources which have not been discovered by File Inventory, and no agent can be identified to collect information for the files. |
| | Purge Maintenance - Incomplete File Upload Sessions | This task removes incomplete file upload sessions older than the specified time period. |
| | Purge Maintenance - Message History | This server task removes all Message History data that is older than the number of seconds/minutes/hours/days/weeks specified. Message History data tracks all events received by the Privilege Manager Server and is used for information purposes. |
| | Purge Old Computers | Remove old computers and gauge data for those old computers. |
| Monitoring | Check for Available Product Updates | Checks the configured nuget:source:SolutionCentre for available product updates. |

## Server Tasks

| Component | Task | Description |
| ----- | ----- | ----- |
| Application Control | Get Security Rating for File | Get/update the security rating for the given file. |
| | Get Security Ratings for Files | Get/update the security ratings for the given files. |
| | Refresh Security Rating Reports | Refreshes old security rating reports for resources rated by the given provider. |
| Application Control Cylance | | |
| Directory Services | Default Import AzureAD Users/Groups | Run this task to import/update Azure AD users and groups. |
| | Default Import Directory | Run this task to import/update directory OUs, users, and containers. |
| | Default Import Directory Computers | Run this task to import/update directory computer resources. |
| | Default Import Directory Sites | Run this task to import/update directory sites. |
| | Import Specific Azure AD Users and Groups | Import specific users and groups from Azure Active Directory. |
| | Merge Duplicate Account SID Resources | Run this task to merge resources that have a duplicate account SID. |
| | Synchronize Organizational Unit Server Task | Synchronize Organizational Unit Server Task. |
| | Update OU Directory Scope Collections Membership | This task updates the membership of Directory Services OU scope collections. |
| | Update OU Directory Scope Collections Membership 2 | This task updates the membership of Directory Services OU scope collections. |
| Email Tasks | Send Gauge Summary E-mail Task | Send a specific report on a schedule. |
| File Inventory | Inventory File | Run this task to collect detailed information on the selected file for reports, filters, etc. |
| | Inventory File Resource | Run this task to update information on an existing file resource for reports, filters, etc. |
| | Inventory Package | Run this task to scan the contents of a package and report detailed information on files it contains for reports, filters, etc. |
| | Inventory Package with Exclusions | Run this task to scan the contents of a package and report detailed information on files it contains for reports, filters, etc. |
| | Inventory Packages | Run this task to scan the contents of a list of packages and report detailed information on files it contains for reports, filters, etc. |
| | Inventory Packages Referenced in Whitelists | Run this task to collect detailed information for files contained in packages referenced in one or more whitelists. |
| | Inventory Uploaded File | This task is used internally to collect detailed information from files uploaded remotely to the server. It is visible only for status information and troubleshooting. |
| Foreign Systems | Sync users with Thycotic One | Run this task to synchronize PM users with a Thycotic One instance. |
| | SCCM | Tasks here let you synchonize users, computers, and specific SCCM collection. |
| | ServiceNow | Creates ServiceNow Approval Request items. |
| | Symantec Management Platform | Tasks here let you synchronize SMP collections and package(s). |
| | Syslog | |
| Local Security | Update Primary User | Updates the primary user for the given computer resource. |
| | Update Primary User for Collection | Updates the primary user for each computer in the given collection. |
| Security | Rebuild Item Security Cache | Run this task to mark all entries in the item security cache as invalid, forcing a rebuild. |
| | Refresh Agent Secrets | Run this task to refresh the agent secrets that were generated before the given max age. |
| | Revoke Agent Secrets | Run this task to revoke the secrets from one or more agents. |
| | Revoke Secrets from All Agents | Run this task to revoke the secrets from all agents. |
| | Set Security Rating | Run this task to manually set the security rating (used in filters) for the selected files. |
| | Update Security Ratings for Resource | Run this task to update the security ratings (used in filters) for the given resources using the given rating system. |
| Utility | Delete Item | This task will delete an item, and optionally dependent children. |
| | Update Server Gauge State | This task will update the state of a server gauge. |
