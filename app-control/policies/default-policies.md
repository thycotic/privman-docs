[title]: # (- List of Default Policies)
[tags]: # (overview,out-of-box)
[priority]: # (4999)
# List of Default Policies

Here is the complete list of policies that come with Privilege Manager out-of-the-box, grouped by folder type. Once you create custom policies they are listed along the default policies under the tab respective to the template used, as the template associates the folder type.

## Process Hardening

| Policy | Description | Type | Priority | Enabled |
| ----- | ----- | ----- | ----- | ----- |
|Remove Advanced Privileges for Interactive Users|Removes advanced privileges for users interacting with a system via Desktop|n/a|50|n|

## System Options

| Policy | Description | Type | Priority | Enabled |
| ----- | ----- | ----- | ----- | ----- |
|Client Option - Elevate Adding Printers via Control Panel|Elevates privileges of users to allow printer drivers to be installed through the Control Panel|Elevate|60|n|
|Client Option - Elevate Adding Printers via PrintUI.exe|Elevates privileges of users to allow printer drivers to be installed by the PrintUI Utility|Elevate|60|n|
|Client Option - Elevate Changing Time and Date|Elevates privileges of users to allow them to change the system time and date|Elevate|60|n|
|Client Option - Elevate Device Pairing|Elevates privileges of users to allow new drivers to be installed during the device pairing wizard.|Elevate|60|n|
|Client Option - Elevate Disk Defragmentation (Vista/7)|Elevates privileges of users to allow them to defragment their hard disks on Windows Vista and Windows 7.|Elevate|60|n|
|Client Option - Elevate Disk Defragmentation (XP)|Elevates privileges of users to allow them to defragment their hard disks on Windows XP.|Elevate|60|n|
|Client Option - Elevate Installing Display Languages|Elevates privileges of users to allow display languages to be installed|Elevate|60|n|
|Client Option - Elevate Network Adapter Settings|Elevates privileges to allow user to change network adapter settings.|Elevate|60|n|
|Client Option - Elevate Resource and Performance Monitoring|Elevates privileges of users to allow them to run Windows Resource and Performance Monitor utilities|Elevate|60|n|
|Client Option - Elevate Windows Backup|Elevates privileges of users to allow them to run Windows Backup|Elevate|60|n|

## Privilege Management

| Policy | Description | Type | Priority | Enabled |
| ----- | ----- | ----- | ----- | ----- |
|Limit Internet Browser and Mail Clients Process Rights|This policy implements the fundamental security principle of least privilege by restricting the process rights for standard Internet browsers and mail clients. Running these applications with administrative rights can present significant security problems. This policy reduces the risk of an exploit infecting a computer from within these applications.|Reduce|50|n|
|Limit Popular Instant Messaging Application Process Rights|This policy implements the fundamental security principle of least privilege by restricting the process rights for instant messaging applications. Running these applications with administrative rights can present significant security problems. This policy reduces the risk of an exploit infecting a computer from within these applications.|Reduce|50|n|
|Limit Popular Media Player Process Rights|This policy implements the fundamental security principle of least privilege by restricting the process rights for media player applications. Running these applications with administrative rights can present significant security problems. This policy reduces the risk of an exploit infecting a computer from within these applications.|Reduce|50|n|
|Limit Process Rights for Unclassified Applications Discovered in the Last Week|This policy implements the fundamental security principle of least privilege by restricting the process rights for an application. Unnecessarily running applications with administrative rights can present significant security problems. This policy reduces the risk of an exploit infecting a computer from within an application. This policy affects applications that have been discovered locally in the last week.|Reduce|95|n|
|User Access Control (UAC) Override Policy|This policy allows standard users to provide a justification for elevation instead of seeing the UAC prompt.|Elevate|15|n|
|User Requested Elevation Justification Policy|This policy allows users to request applications to run with Administrative Rights if they provide a justification.|Elevate|15|n|

## Application Analysis

| Policy | Description | Type | Priority | Enabled |
| ----- | ----- | ----- | ----- | ----- |
|Administrative Rights Required Detection Policy (Application Compatibility)|This policy detects applications that are deemed to require Administrative rights by Windows.|Elevate|45|n|
|Administrative Rights Required Detection Policy (Security Manifest)|This policy detects applications that contain a security manifest that specifies administrative rights are required.|Elevate|45|n|
|Event Discovery Audit Elevated Privileges Policy|This policy will detect all applications that are run with Administrator Rights on endpoints with the agent. This policy can be configured on the Event Discovery Configuration page.| |45|n|
|Setup Detection Policy|This policy reports on applications that are detected as an installer.| |45|n|

## Windows Policies

| Policy | Description | Type | Priority | Enabled |
| ----- | ----- | ----- | ----- | ----- |
|Event Discovery Testing Computers Audit Policy (Windows)|This policy is enabled through the Event Discovery configuration by enabling the option to log all activity from the test group.| 97|n|

## macOS Policies

| Policy | Description | Type | Priority | Enabled |
| ----- |  ----- |  ----- |  ----- |  ----- |
| Event Discovery Testing Computers Audit Policy (MacOS) | This policy is enabled through the Event Discovery configuration by enabling the option to log all activity from the test group. | | 97 | n |

## Automatic Elevation via Windows Client System Settings

Common Windows client settings can be deployed to endpoint agents the same way as any policy. These settings target __All__ Windows Computers with Application Control Agent Installed (Target)" as the default resource target. Once a setting is selected from the list, the resource target can be modified to include specific computer or other existing resource targets can be assigned on screen.

| Policy | Description |
|  ----- |  ----- |
| Add Devices | Allow users to add drivers, installing drivers as necessary. |
| Add Printers | Allow users to add printers, installing drivers as necessary. |
| Backup the System | Allow users to perform system backup operations. |
| Change the Date and Time | Allow users to change the date, time and timezone. |
| Change Network Adapter Settings | Allow users to change the network adapter settings. |
| Defragment the Disk | Allow users to perform disk defragmentation operations. |
| Install Language Packs | Allow users to install operating system display languages. |
| Monitor Performance | Allow users to run the Windows Performance Monitor utility. |

## ActiveX

ActiveX Setting define which sites can run ActiveX controls for standard users.

To create an ActiveX setting, a new policy must be created based on the ActiveX policy type template.

## Firewall

An Application Firewall Policy policy type allows for firewall rules to be applied as an Action in an Application Control Policy.

To create Firewall rules, a new policy must be created based on the Windows Application Policy type template.

When defining the Firewall Policy an Application Classification must be set. An Action of type Application Classification can then apply that classification to an Application Control Policy, which then enforces all of the defined Firewall Policies that are defined with that classification.

## General

The policies available on the General tab are covering the basic Privilege Manager functionality and are enabled by default. Most of these policies are fulfilling utility functions otherwise also considered tasks.

| Policy | Description |
|  ----- |  ----- |
| Basic Inventory (Initial, Mac OS) | This scheduled task triggers the Agent to send Mac OS basic inventory. This policy takes an inventory as soon at the agent and the initial policies are deployed and should be removed from the machines afterwards. |
| Basic Inventory (Initial, Windows) | Instructs computers to report the Win32_ComputerSystem, Win32_ComputerSystemProduct and Win32_OperatingSystem WMI classes to the server. This policy takes an inventory as soon at the agent and the initial policies are deployed and should be removed from the machines afterwards. |
| Basic Inventory (Mac OS) | This scheduled task triggers the Agent to send Mac OS basic inventory. |
| Basic Inventory (Windows) | Instructs computers to report changes to their Win32_ComputerSystem, Win32_ComputerSystemProduct and Win32_OperatingSystem WMI classes to the server on a scheduled basis, like once a week for example. |
| Cleanup Agent Inventory Transfers (Windows) | Completes and cleans BITS transfers and temporary files used by the TMS Agent Inventory Helper. |
| Cleanup sent Privilege Manager Events (Mac OS) | Purges Agent events that have been successfully transmitted from managed endpoints to reclaim disk space. |
| Cleanup sent Privilege Manager Events (Windows) | Purges Agent events that have been successfully transmitted from managed endpoints to reclaim disk space. |
| Default File Inventory Policy (MacOS) | The purpose of this policy is to inventory software programs running on the managed computer. |
| Default File Inventory Policy (Windows) | The purpose of this policy is to inventory software programs running on the managed computer. |
| Ensure UAC Override Setting (Windows) | Ensures that the UAC Override Registry Key is set. |
| Local User Inventory Policy | The purpose of this policy is to inventory Local User account, groups and group membership on the client. This policy can also be used to inventory for specific account privileges. |
| Local User Inventory Policy (MacOS) | The purpose of this policy is to inventory Local User account, groups and group membership on the client. This policy can also be used to inventory for specific account privileges. |
| Perform Resource Discovery (Mac OS) | Schedule on which agents will check with server to determine if any local resources require discovery. |
| Perform Resource Discovery (Windows) | Schedule on which agents will check with server to determine if any local resources require discovery. |
| Retry errored TMS Events (Mac OS) | Scan Agent queue for any events that require retransmission. |
| Retry errored TMS Events (Windows) | Scan Agent queue for any events that require retransmission. |
| Scheduled Check Pending Client Tasks - Internet Clients (Windows) | Initiate a check for pending client tasks. Used by agents that are unable to receive an incoming connection from the server. |
| Scheduled Registration - Internet Clients (Windows) | Initiate agent registration with server less frequently than internal clients. |
| Scheduled Registration (Mac OS) | When this policy is triggered the Agent will attempt (or re-attempt) to register with the server. |
| Scheduled Registration (Windows) | Initiate agent registration with server. |
| Update Agent Commands (Mac OS)  | When this policy is triggered the Agent will update agent command items. |
| Update Agent Commands (Windows) | Instructs Agent to update any agent commands if required. |
| Update Applicable Policies (Mac OS) | When this policy is triggered the Agent will check the server for updated policies. |
| Update Applicable Policies (Windows) | When this policy is triggered the Agent will check the server for updated policies. |
| Update Applicable Policies - Internet Clients (Windows) | Instructs Agent to check with server for policy changes less frequently than internal clients. |
| Update Provisioned Resource Client Items (MacOS) | |
| Update Provisioned Resource Client Items (Windows) | |
| User Logon Inventory Policy | Updates user logon data on the given schedule. |
| Windows Service Inventory Policy | The purpose of this policy is to inventory Windows Services on the client. |

### Not Enabled

| Policy | Description |
|  ----- |  ----- |
| COM Inventory Policy | The purpose of this policy is to inventory COM+ and DCOM packages installed on the client. |
| Disable Local Guest Accounts | Provisioning policy to disable local Guest accounts on Windows computers. |
| Randomize Administrator Password | |
| Shared Folder Inventory Policy | The purpose of this policy is to inventory shared folders on the client. |
