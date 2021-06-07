[title]: # (Server Tasks)
[tags]: # (default)
[priority]: # (2)
# Server Tasks

## Component Based List of Default Tasks

| Component | Task | Description |
| ----- | ----- | ----- |
| Application Control | Get Security Rating for File | Get/update the security rating for the given file. |
| | Get Security Ratings for Files | Get/update the security ratings for the given files. |
| | Refresh Security Rating Reports | Refreshes old security rating reports for resources rated by the given provider. |
| Application Control Cylance | | |
| [Email Tasks](../scheduled/email-reports.md) | Send Gauge Summary E-mail Task | Send a specific report on a schedule. |
| File Inventory | Inventory File | Run this task to collect detailed information on the selected file for reports, filters, etc. |
| | Inventory File Resource | Run this task to update information on an existing file resource for reports, filters, etc. |
| | Inventory Package | Run this task to scan the contents of a package and report detailed information on files it contains for reports, filters, etc. |
| | Inventory Package with Exclusions | Run this task to scan the contents of a package and report detailed information on files it contains for reports, filters, etc. |
| | Inventory Packages | Run this task to scan the contents of a list of packages and report detailed information on files it contains for reports, filters, etc. |
| | Inventory Packages Referenced in Allow Lists | Run this task to collect detailed information for files contained in packages referenced in one or more allow lists. |
| | Inventory Uploaded File | This task is used internally to collect detailed information from files uploaded remotely to the server. It is visible only for status information and troubleshooting. |
| Foreign Systems | | |
| | Refer to | [Directory Services](fs-ds.md) for details on the following Directory Services Tasks |
| Directory Services | Import Directory | Run this task to import/update directory OUs, users, and containers. |
| | Import Directory Computers | Run this task to import/update directory computer resources. |
| | Import Directory Sites | Run this task to import/update directory sites. |
| | Import Specific Azure AD Users and Groups | Import specific users and groups from Azure Active Directory. |
| | Synchronize Organizational Unit Server Task | Synchronize Organizational Unit Server Task. |
| | Update OU Directory Scope Collections Membership | This task updates the membership of Directory Services OU scope collections. |
| | Update OU Directory Scope Collections Membership 2 | This task updates the membership of Directory Services OU scope collections. |
| DS - Maintenance | Delete Imported Azure AD Resources | This task will delete users, groups, and devices from Privilege Manager that were imported from Azure AD. |
| | Refer to | [Directory Services Maintenance](fs-ds-maint.md) for details on the following Directory Services Maintenance Tasks |
| | Delete Imported Directory Resources | This task will delete users, groups, computers, OUs, and Sites from Privilege Manager that were imported from AD. |
| | Merge Computers with Duplicate Azure Device IDs | This task will merge computers with duplicate Azure AD Device IDs. |
| | Merge Duplicate Account SID Resources | Run this task to merge resources that have a duplicate account SID. |
| | OU Directory Scope Collection Update | This task updates the membership of Directory Services OU scope collections based on a selected Schedule Type. |
| | Update OU Directory Scope Collections Membership | This task updates the membership of Directory Services OU scope collections. |
| | Update OU Directory Scope Collections Membership 2 | This task updates the membership of Directory Services OU scope collections. |
| Obsolete | Import Azure Ad Users/Groups | This task is obsolete and should not be used anymore. |
| | [SCCM](../../config/foreign-systems/third-party/set-up-sccm.md) | Tasks here let you synchronize users, computers, and specific SCCM collection. |
| | [ServiceNow](../../config/foreign-systems/third-party/set-up-servicenow.md) | Creates ServiceNow Approval Request items. |
| | [Symantec Management Platform](../../config/foreign-systems/third-party/set-up-smp.md) | Tasks here let you synchronize SMP collections and package(s). |
| | [Syslog](../../config/foreign-systems/third-party/set-up-syslog.md) | Creates tasks to send events to the configured syslog server based on specific templates.  |
| Local Security | Update Primary User | Updates the primary user for the given computer resource. |
| | Update Primary User for Collection | Updates the primary user for each computer in the given collection. |
| Thycotic One Users | Sync users with Thycotic One | Run this task to synchronize PM users with a Thycotic One instance. |
| Security | Rebuild Item Security Cache | Run this task to mark all entries in the item security cache as invalid, forcing a rebuild. |
| | Refresh Agent Secrets | Run this task to refresh the agent secrets that were generated before the given max age. |
| | Revoke Agent Secrets | Run this task to revoke the secrets from one or more agents. |
| | Revoke Secrets from All Agents | Run this task to revoke the secrets from all agents. |
| | Set Security Rating | Run this task to manually set the security rating (used in filters) for the selected files. |
| | Update Security Ratings for Resource | Run this task to update the security ratings (used in filters) for the given resources using the given rating system. |
| Utility | Delete Item | This task will delete an item, and optionally dependent children. |
| | [Reset Licensing](../reset-license.md) | This task will reset licensing, deleting all installed license keys. |
| | Update Server Gauge State | This task will update the state of a server gauge. |
