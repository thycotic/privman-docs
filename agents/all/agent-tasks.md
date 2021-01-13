[title]: # (Agent Tasks)
[tags]: # (endpoints)
[priority]: # (8)
# Agent Specific Tasks

Certain Privilege Manager tasks are directly related to agent processes and their operational loads.

Server side tasks, also known as Remote Client Scheduled Commands do not require a policy. Agent tasks require a policy. These types of tasks are with the exception of one, by default enabled and run on a scheduled basis. Most are read-only system tasks, that can be copied, renamed, and then customized.

The majority will run for the first time after system initialization.

## Windows Remote Client Scheduled Commands

| Name | Description | Schedule | Enabled |
| ----- | ----- | ----- | ----- |
| [Restrict Account Permissions on Agent Services (Windows)](../win/agent-hardening.md) | Instructs computers to only allow the specified users to start and stop the Thycotic services. | n/a | No |
| [Basic Inventory (Initial, Windows)](../../admin/tasks/client/bi.md) | Instructs computers to report the Win32_ComputerSystem, Win32_ComputerSystemProduct and Win32_OperatingSystem WMI classes to the server. | daily | Yes |
| [Basic Inventory (Windows)](../../admin/tasks/client/bi.md) | Instructs computers to report the Win32_ComputerSystem, Win32_ComputerSystemProduct and Win32_OperatingSystem WMI classes to the server. | daily | Yes |
| [Cleanup Agent Inventory Transfers (Windows)](../../admin/tasks/client/cait.md) | Completes and cleans BITS transfers and temporary files used by the TMS Agent Inventory Helper. | daily  | Yes |
| [Cleanup sent Privilege Manager Events (Windows)](../../admin/tasks/client/cpme.md) | Purges Agent events that have been successfully transmitted from managed endpoints to reclaim disk space. | daily | Yes |
| [Configure Privilege Manager Remove Programs](../../admin/tasks/client/cpmrp.md) | Configure the Privilege Manager Remove Programs behavior. | daily | Yes |
| [Default File Inventory Policy (Windows)](../../admin/tasks/client/dfip.md) | The purpose of this policy is to inventory software programs running on the managed computer. | weekly | Yes |
| [Deploy File Hash Exclusion Setting (Windows)](../../admin/tasks/client/exclude-from-file-hash.md) | The purpose of this policy is to provide the ability to exclude certain file extensions from the hash process. | daily | No |
| [Ensure UAC Override Setting (Windows)](../../admin/tasks/client/euacos.md) | Ensures that the UAC Override Registry Key is set. | daily | Yes |
| [Local User Inventory Policy](../../admin/tasks/client/luip.md) | The purpose of this policy is to inventory Local User account, groups and group membership on the client. This policy can also be used to inventory for specific account privileges. | weekly | Yes |
| [Perform Resource Discovery (Windows)](../../admin/tasks/client/prd.md) | Schedule on which agents will check with server to determine if any local resources require discovery. | daily | Yes |
| [Retry errored TMS Events (Windows)](../../admin/tasks/client/retmse.md) | Scan Agent queue for any events that require retransmission. | daily | Yes |
| [Scheduled Check Pending Client Tasks - Internet Clients (Windows)](../../admin/tasks/client/scfpt.md) | Initiate a check for pending client tasks. Used by agents that are unable to receive an incoming connection from the server. | daily | Yes |
| [Scheduled Registration - Internet Clients (Windows)](../../admin/tasks/client/sr.md) | Initiate agent registration with server less frequently than internal clients. | daily | Yes |
| [Scheduled Registration (Windows)](../../admin/tasks/client/sr.md) | Initiate agent registration with server. | daily | Yes |
| [Update Agent Commands (Windows)](../../admin/tasks/client/uac.md) | Instructs Agent to update any agent commands if required. | daily | Yes |
| [Update Applicable Policies - Internet Clients (Windows)](../../admin/tasks/client/uap.md) | Instructs Agent to check with server for policy changes. | daily | Yes |
| [Update Applicable Policies (Windows)](../../admin/tasks/client/uap.md) | Instructs Agent to check with server for policy changes. | daily | Yes |
| [Update Provisioned Resource Client Items (Windows)](../../admin/tasks/client/uprci.md) |  | daily | Yes |
| [User Logon Inventory Policy](../../admin/tasks/client/ulip.md) | Updates user logon data on the given schedule. | weekly | Yes |
| [Windows Service Inventory Policy](../../admin/tasks/client/wsip.md) | The purpose of this policy is to inventory Windows Services on the client. | weekly | Yes |

## MacOS Remote Client Scheduled Commands

| Name | Description | Schedule | Enabled |
| ----- | ----- | ----- | ----- |
| [Basic Inventory (Initial, Mac OS)](../../admin/tasks/client/bi.md) | This scheduled task triggers the Agent to send Mac OS basic inventory. | daily | Yes |
| [Basic Inventory (Mac OS)](../../admin/tasks/client/bi.md) | This scheduled task triggers the Agent to send Mac OS basic inventory. | daily | Yes |
| [Cleanup sent Privilege Manager Events (Mac OS)](../../admin/tasks/client/cpme.md) | Purges Agent events that have been successfully transmitted from managed endpoints to reclaim disk space. | daily | Yes |
| [Default File Inventory Policy (MacOS)](../../admin/tasks/client/dfip.md) | The purpose of this policy is to inventory software programs running on the managed computer. | weekly | Yes |
| [Ignore macOS Catalina software update (Mac OS)](../../admin/tasks/client/ignore-os-updates.md) | The purpose of this policy is to provide a way in Privilege Manager to ignore macOS updates. | daily | no |
| [Local User Inventory Policy (MacOS)](../../admin/tasks/client/luip.md) | The purpose of this policy is to inventory Local User account, groups and group membership on the client. This policy can also be used to inventory for specific account privileges. | weekly | Yes |
| [Perform Resource Discovery (Mac OS)](../../admin/tasks/client/prd.md)]| Schedule on which agents will check with server to determine if any local resources require discovery. | daily | Yes |
| [Reset ignored macOS software updates (Mac OS)](../../admin/tasks/client/ignore-os-updates.md) | The purpose of this policy is to provide a way in Privilege Manager to reset ignored macOS updates. | daily | No |
| [Retry errored TMS Events (Mac OS)](../../admin/tasks/client/retmse.md) | Scan Agent queue for any events that require retransmission. | daily | Yes |
| [Scheduled Registration (Mac OS)](../../admin/tasks/client/sr.md) | When this policy is triggered the Agent will attempt (or re-attempt) to register with the server. | daily | Yes |
| [Update Agent Commands (Mac OS)](../../admin/tasks/client/sr.md) | When this policy is triggered the Agent will update agent command items. | daily | Yes |
| [Update Applicable Policies (Mac OS)](../../admin/tasks/client/uap.md) | When this policy is triggered the Agent will check the server for updated policies. | daily | Yes |
| [Update Provisioned Resource Client Items (MacOS)](../../admin/tasks/client/uprci.md) | | daily | Yes |

## Unix/Linux Remote Client Scheduled Commands

| Name | Description | Schedule | Enabled |
| ----- | ----- | ----- | ----- |
| [Scheduled Check for Pending Tasks (Unix/Linux)](../../admin/tasks/client/scfpt.md) | This remote-scheduled task checks for server-scheduled tasks assigned to the agent. | daily | Yes |
| [Scheduled Registration (Unix/Linux)](../../admin/tasks/client/sr.md) | This agent-scheduled task refreshes registration data for the assigned agents. | daily | Yes |
| [Update Applicable Policies (Unix/Linux)](../../admin/tasks/client/uap.md) | This remote-scheduled command will update policies applicable to the assigned agents. | daily | Yes |
