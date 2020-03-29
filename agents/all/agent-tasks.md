[title]: # (Agent Tasks)
[tags]: # (endpoints)
[priority]: # (8)
# Agent Specific Tasks

Certain Privilege Manager tasks are directly relating to agent processes and their operational loads.

Server side tasks, also known as Remote Client Scheduled Commands do not require a policy. Agent tasks require a policy. These types of tasks are with the exception of one, by default enabled and run on a scheduled basis. Most are read-only system tasks, that can be copied, renamed, and then customized.

The majority will run for the first time after system initialization.

## Windows Remote Client Scheduled Commands

| Name | Description | Schedule | Enabled |
| ----- | ----- | ----- | ----- |
| Agent Service Start / Stop Control (Windows) | Instructs computers to only allow the specified users to start and stop the Thycotic services. | n/a | N |
| [Basic Inventory (Initial, Windows)](../../tasks/client/bi.md) | Instructs computers to report the Win32_ComputerSystem, Win32_ComputerSystemProduct and Win32_OperatingSystem WMI classes to the server. | daily | Y |
| [Basic Inventory (Windows)](../../tasks/client/bi.md) | Instructs computers to report the Win32_ComputerSystem, Win32_ComputerSystemProduct and Win32_OperatingSystem WMI classes to the server. | daily | Y |
| [Cleanup Agent Inventory Transfers (Windows)](../../tasks/client/cait.md) | Completes and cleans BITS transfers and temporary files used by the TMS Agent Inventory Helper. | daily  | Y |
| [Cleanup sent Privilege Manager Events (Windows)](../../tasks/client/cpme.md) | Purges Agent events that have been successfully transmitted from managed endpoints to reclaim disk space. | daily | Y |
| [Configure Privilege Manager Remove Programs](../../tasks/client/cpmrp.md) | Configure the Privilege Manager Remove Programs behavior. | daily | Y |
| [Default File Inventory Policy (Windows)](../../tasks/client/dfip.md) | The purpose of this policy is to inventory software programs running on the managed computer. | weekly | Y |
| [Ensure UAC Override Setting (Windows)](../../tasks/client/euacos.md) | Ensures that the UAC Override Registry Key is set. | daily | Y |
| [Local User Inventory Policy](../../tasks/client/luip.md) | The purpose of this policy is to inventory Local User account, groups and group membership on the client. This policy can also be used to inventory for specific account privileges. | weekly | Y |
| [Perform Resource Discovery (Windows)](../../tasks/client/prd.md) | Schedule on which agents will check with server to determine if any local resources require discovery. | daily | Y |
| [Retry errored TMS Events (Windows)](../../tasks/client/retmse.md) | Scan Agent queue for any events that require retransmission. | daily | Y |
| [Scheduled Check Pending Client Tasks - Internet Clients (Windows)](../../tasks/client/scfpt.md) | Initiate a check for pending client tasks. Used by agents that are unable to receive an incoming connection from the server. | daily | Y |
| [Scheduled Registration - Internet Clients (Windows)](../../tasks/client/sr.md) | Initiate agent registration with server less frequently than internal clients. | daily | Y |
| [Scheduled Registration (Windows)](../../tasks/client/sr.md) | Initiate agent registration with server. | daily | Y |
| [Update Agent Commands (Windows)](../../tasks/client/uac.md) | Instructs Agent to update any agent commands if required. | daily | Y |
| [Update Applicable Policies - Internet Clients (Windows)](../../tasks/client/uap.md) | Instructs Agent to check with server for policy changes. | daily | Y |
| [Update Applicable Policies (Windows)](../../tasks/client/uap.md) | Instructs Agent to check with server for policy changes. | daily | Y |
| [Update Provisioned Resource Client Items (Windows)](../../tasks/client/uprci.md) |  | daily | Y |
| [User Logon Inventory Policy](../../tasks/client/ulip.md) | Updates user logon data on the given schedule. | weekly | Y |
| [Windows Service Inventory Policy](../../tasks/client/wsip.md) | The purpose of this policy is to inventory Windows Services on the client. | weekly | Y |

## MacOS Remote Client Scheduled Commands

| Name | Description | Schedule | Enabled |
| ----- | ----- | ----- | ----- |
| [Basic Inventory (Initial, Mac OS)](../../tasks/client/bi.md) | This scheduled task triggers the Agent to send Mac OS basic inventory. | daily | Y |
| [Basic Inventory (Mac OS)](../../tasks/client/bi.md) | This scheduled task triggers the Agent to send Mac OS basic inventory. | daily | Y |
| [Cleanup sent Privilege Manager Events (Mac OS)](../../tasks/client/cpme.md) | Purges Agent events that have been successfully transmitted from managed endpoints to reclaim disk space. | daily | Y |
| [Default File Inventory Policy (MacOS)](../../tasks/client/dfip.md) | The purpose of this policy is to inventory software programs running on the managed computer. | weekly | Y |
| [Local User Inventory Policy (MacOS)](../../tasks/client/luip.md) | The purpose of this policy is to inventory Local User account, groups and group membership on the client. This policy can also be used to inventory for specific account privileges. | weekly | Y |
| [Perform Resource Discovery (Mac OS)](../../tasks/client/prd.md)]| Schedule on which agents will check with server to determine if any local resources require discovery. | daily | Y |
| [Retry errored TMS Events (Mac OS)](../../tasks/client/retmse.md) | Scan Agent queue for any events that require retransmission. | daily | Y |
| [Scheduled Registration (Mac OS)](../../tasks/client/sr.md) | When this policy is triggered the Agent will attempt (or re-attempt) to register with the server. | daily | Y |
| [Update Agent Commands (Mac OS)](../../tasks/client/sr.md) | When this policy is triggered the Agent will update agent command items. | daily | Y |
| [Update Applicable Policies (Mac OS)](../../tasks/client/uap.md) | When this policy is triggered the Agent will check the server for updated policies. | daily | Y |
| [Update Provisioned Resource Client Items (MacOS)](../../tasks/client/uprci.md) | | daily | Y |

## Unix/Linux Remote Client Scheduled Commands

| Name | Description | Schedule | Enabled |
| ----- | ----- | ----- | ----- |
| [Scheduled Check for Pending Tasks (Linux)](../../tasks/client/scfpt.md) | This remote-scheduled task checks for server-scheduled tasks assigned to the agent. | daily | Y |
| [Scheduled Registration (Linux)](../../tasks/client/sr.md) | This agent-scheduled task refreshes registration data for the assigned agents. | daily | Y |
| [Update Applicable Policies (Linux)](../../tasks/client/uap.md) | This remote-scheduled command will update policies applicable to the assigned agents. | daily | Y |
