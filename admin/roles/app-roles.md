[title]: # (Application Roles)
[tags]: # (access)
[priority]: # (2)
# Application Roles

The following table provides an overview of Privilege Manager Application Roles:

| Role | Summary | CRUD Users/Groups | View Reports | Run Tasks | Approve Approval Requests | Disclose Passwords | Modify  Config, View Install Codes | Modify Policies, Filters, and LSS | View All Items | Upload Files | Create or Revoke Install Codes |
| ----- | ----- | ----- | ----- | ----- | ----- | ----- | ----- | ----- | ----- | ----- | ----- |
| Privilege Manager Administrators | Can do anything. | yes | yes | yes | yes | yes | yes | yes | yes | yes | yes |
| Privilege Manager Field Engineering | Cannot do anything out of the box. Reserved for future use.  |  |  |  |  |  |  |  |  |  |  |
| Privilege Manager Helpdesk Users | This role has the least permissions. It can disclose passwords and manage approvals only. |  |  |  | yes | yes |  |  |  |  |  |
| Privilege Manager MacOS Administrators | Can do anything an administrator can, but only for macOS policies and resource targets. | yes (macOS) | yes | yes | yes | yes | yes | yes (macOS) | yes | yes | yes |
| Privilege Manager Users | This is a read only role that can view all items, disclose passwords, and manage approvals. |  | yes |  | yes | yes |  |  | yes |  |  |
| Privilege Manager Windows Administrators | Can do anything an administrator can, but only for Windows policies and resource targets. | yes (Win) | yes | yes | yes | yes | yes | yes (Win) | yes | yes | yes |
