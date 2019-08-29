[title]: # (Feature Overview)
[tags]: # (intro)
[priority]: # (98)
# Feature Overview

## Active Directory (On-premises; Azure AD coming with 10.6)

For those organizations leveraging Active Directory (AD) as their identity authentication and authorization service, deploying a least privilege program that works seamlessly with AD is absolutely critical. Privilege Manager integrates with AD so administrators can synchronize Domain Objects such as computers, OUs, and security groups from AD with their application control policies. Privilege Manager can leverage the user, group and privilege associations managed by Active Directory in its policy deployment and ensure unauthorized changes to AD made by endpoint users – such as adding a user to a local administrator account – can't be blocked automatically and in real time.

## Agent & OS Reports

The lightweight Privilege Manager agent is a critical component of Thycotic's application control, giving you the ability to evaluate the health and status of agents in real time.  Privilege Manager provides pre-configured and fully customizable reporting on the status of agents and endpoint operating systems. In the Privilege Manager reporting dashboard, you can drill into reports based on any dimension and easily export report data to other reporting applications or Excel.

## Application Discovery for Administrative or Root Privileges

The most powerful applications installed on endpoints are those that require administrator credentials or root privileges to run. Privilege Manager discovers all applications that run on endpoints through its Learning Mode, giving you a precise snapshot of how these applications are used before you implement any changes. You can set up Discovery policies to target any new application action that requires administrator or root access, so no privileged action goes unnoticed.

Non-Domain Endpoint Support - Privilege Manager provides management and application control support for endpoints even if they are not associated with your organizational network. Because it utilizes a lightweight agent it can manage endpoints outside the network – such as those used by vendors, contractors, and partners - with the same dexterity and precision control as those within the network.

## Automated Local Account Password Rotation

Rotate local account passwords on endpoints based on a pre-defined, fully customizable schedule, ensuring that password best practices are followed.

## Centralized Application & Execution Event Logging

Privilege Manager can record all executable events on managed endpoints so you can review, search, and analyze these logs in a unified manner without leaving the console.

## Child Process Control

Child processes are those that execute from within a file such as a PDF and are frequently how malware executes on an endpoint. Privilege Manager allows you to prohibit execution of Child Process to ensure unknown executables are restricted on your organization's network.

## Custom & Scheduled Reports

Privilege Manager's ability to quickly generate fully customized reports and schedule the execution and delivery of these reports is essential to maintaining a real-time understanding of every aspect of your least privilege program.

## Define Local Group Membership

Review and manage local groups, including Group membership. This powerful capability prevents Group membership changes from being made on an endpoint, as all changes must be made via the Privilege Manager console.

## End-user Justification & Admin Approval Workflow

This policy type requires that people provide a justification for why they need to run an application before elevating with administrator privileges. User Justification refers to the policy action. Since Conditions and Actions are independent, this action can be applied to any condition.

## Flexible Policy Deployment Configuration

Enforce least privilege through policies for application control. You'll start with access to a broad library of out-of-the-box policies, all of which are completely customizable. Layered policies create the parameters that dictate precisely how privileges are accessed across your network. They define what actions people can run, and where. When policy conditions are met, Privilege Manager automatically applies an action (e.g. blacklisting, whitelisting, application elevation, etc.) on one or multiple assets.

## High Availability & Load Balancing

Web server clustering provides both high availability and load balancing by allowing multiple web servers to run Privilege Manager software. A clustered environment is key in disaster recovery scenarios as you can automatically failover to a separate web server with no downtime. Additionally, performance can be improved through load balancing by having multiple servers processing requests simultaneously.

## Local Admin Rights Removal

Privilege Manager can automatically revoke all local administrative privileges on endpoints so you can adhere to a least privilege policy. With application-level privilege elevation, user-level privileges are not required and people can still access all the systems they need.

## Local User Account Management

You can manage all local users on all endpoints across your organization, including the automatic rotation of local user password(s), all from a central console.

## Local User & Group Activity Auditing

The ability to audit and review the activity of local users and groups is essential to retroactively identify problematic activity and reduce risk. Privilege Manager lets you swiftly review and search across all User and Group activity associated with privilege escalation on every managed endpoint.

## Privilege Manager Mobile App

The Privilege Manager mobile app for iOS and Android lets you  manage endpoints, configure policies, process approvals, and receive event alerts via a mobile device so you can learn of requests and address issues quickly.

## Real-time Application Analysis | Reputation Check

Privilege Manager integrates with reputation checking software like VirusTotal to provide application analysis in real time. This unique feature allows for reputation analysis of any unknown applications in order to mitigate risk of endpoint attacks from ransomware, zero-day attacks, drive-by downloads, and other unknown malicious software. With Privilege Manager, all applications that meet a general condition (i.e. executed from a specific directory or directories, file names, types, or any applications that are disassociated with existing policies) can be sent to VirusTotal for a reputation check and analysis.

## Responsive & Actionable Reporting Dashboard

Successful application control demands that you have a complete, real-time understanding of the status and activity of all endpoints. Privilege Manager provides a unified reporting dashboard so you can quickly evaluate the status of endpoints, review activity logs and event data, and access a broad library of reports. Responsive and fully configurable, Privilege Manager's dashboard reporting enables you to quickly drill down into reports across any dimension (time, geo-region, OS, status…) to evaluate activities and trends. From the dashboard you can also set up automated alerts to stay informed of potential problems.

## Reverse Proxying

Many organizations choose to protect their Privilege Manager web server by restricting it from direct outbound internet access. To secure your environment according to best practices, it is not enough to simply set your server offline because Privilege Manager still will communicate directly to agents across your network that DO have direct internet access, therefore attackers can potentially use the connection between your endpoint agent and Privilege Manager to breach your web server. To prevent this direct connection between agent endpoints and your Privilege Manager web server, Privilege Managers allows for the setup of a Reverse Proxy machine with limited permissions. A properly configured Reverse Proxy will act as a buffer between Privilege Manager agents and the Privilege Manager server to limit server exposure.

## Sandboxing

Sandboxing quarantines applications so they are not allowed to execute, or only allowed to execute in a limited way so they don’t touch any system folders or underlying OS configurations.  Privilege Manager supports sandboxing for applications that are not known, to ensure they do not negatively impact productivity or introduce threats to the endpoint or network.

## ServiceNow

Many organizations leverage ticketing systems to streamline their support workflow and like to view and report on all support requests within a single system. Privilege Manager can be fully integrated into ServiceNow, so support requests and IT responses can be managed, tracked, and reported via the ticketing system itself.

## Symantec Enterprise Platform (SEP)

For those organizations utilizing the Symantec Endpoint Protection or Symantec Endpoint Protection Cloud solution for whitelisting and reputation, Privilege Manager can utilize the SEP whitelist and reputation engine to inform and prescribe its provision of application control capabilities across endpoints.

## SysLog / SIEM

You can integrate your least privilege and application control program with a SIEM tool or other cyber security reporting and analytics services and tools. Privilege Manager can push out SysLog messages on a fully configurable schedule to any application or service that accepts the SysLog format.

## System Center Configuration Manager (SCCM)

Privilege Manager can integrate with Microsoft System Center Configuration Manager and scan SCCM software delivery “packages” for applications that can be whitelisted by Privilege Manager.

## Tailored Whitelist, Blacklist, Elevation, and Greylisting Policies

Privilege Manager supports whitelisting to ensure that known, trusted applications are fully supported, blacklisting to deny known malicious applications based on attributes, file hash, location, or certificates, and greylisting to prevent unknown applications from running. Greylisting provides a system for discovering the unknowns and adding an action that hinges on a reputation check. Distinct from whitelisting, which allows applications to run with default user level privileges, an elevation policy applies admin credentials to specified applications. This type of policy is often paired with whitelisting so that employees can perform trusted tasks that require administrator credentials to complete, like installing a trusted application (Adobe) or device (printer), without involving IT support.

## User Account Control (UAC) Override

By only elevating application privileges based upon specific policies and criteria, Privilege Manager ensures people don't use Microsoft's UAC capabilities to grant a dangerous or unknown application administrative rights under any circumstance.

## VirusTotal

People sometimes want to run applications and operations on their endpoints that are not on the your approved list of executables. To avoid productivity loss, these unknown applications can be evaluated by 3rd party file and URL analysis service to determine whether they should be allowed to execute. Privilege Manager integrates with leading service VirusTotal so all executables not explicitly on your whitelist or blacklist can be evaluated in near real time.

## Windows & Mac Account Discovery on Endpoints

Privilege Manager identifies all local accounts on agent-installed endpoints and flags those with local admin rights, including hidden or hardcoded admin privileges. A single, comprehensive view makes management easy.
