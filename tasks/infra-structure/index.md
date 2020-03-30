[title]: # (Infrastructure Scheduled Activities)
[tags]: # (default)
[priority]: # (4)
# Infrastructure Scheduled Activities

These are tasks that pertain to either core functions or to components and subcomponents of Privilege Manager.

| Component | Task | Description |
| ----- | ----- | ----- |
| Core, no folder at root level | Client Items Update __OBSOLETE WITH v 10.7 and higher__ | Updates client items required by agents. |
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
| [Maintenance Tasks](../maintenance.md) | Assign Orphaned Agent Uploads | This task assigns agent event uploads that have been orphaned. |
| | Delete Old Performance Counter Events | This task deletes internal performance counter events last updated before the specified time. |
| | Purge Maintenance - Agent Logs | This server task removes all Agent Log data that is older than the time period specified. |
| | Purge Maintenance - Application Control Events | Purges the selected Application Control Event types from the database based on the time range specified. |
| | Purge Maintenance - Audit Events | This task removes audit event records older than the specified time period. |
| | Purge Maintenance - Completed File Upload Sessions | This task removes completed file upload sessions older than the specified time period.|
| | Purge Maintenance - Files Undiscovered | Run this task to delete file resources which have not been discovered by File Inventory, and no agent can be identified to collect information for the files. |
| | Purge Maintenance - Incomplete File Upload Sessions | This task removes incomplete file upload sessions older than the specified time period. |
| | Purge Maintenance - Message History | This server task removes all Message History data that is older than the number of seconds/minutes/hours/days/weeks specified. Message History data tracks all events received by the Privilege Manager Server and is used for information purposes. |
| | Purge Old Computers | Remove old computers and gauge data for those old computers. |
| Monitoring | Check for Available Product Updates | Checks the configured `nuget:source:SolutionCentre` for available product updates. |