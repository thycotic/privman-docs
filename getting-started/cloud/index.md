[title]: # (Cloud)
[tags]: # (initial login)
[priority]: # (1)
# Getting Started Overview - Cloud

The following topics provide a guided path through the instance setup and subsequent initial sign-in steps of a cloud Privilege Manager instance.

* [Cloud Quickstart Guide](cloud-quickstart.md)
* [Cloud Login](cloud-init.md)
* [Agents Installation](../../install/agents/index.md)

  * [Setting the Server Address for Privilege Manager Agents](../../agents/all/agent-set-server-address.md), if the address provided during the agent installation requires updates.

>**Note**: If you are targeting macOS based endpoints, refer to [Getting Started with macOS](../../platforms/macOS/bp/cfg-profiles/index.md).

## Cloud Specific vs. On-prem

The new Privilege Manager Application Programming Interface is by default available on all cloud instances upgraded to 10.8 or newly created.

The following features and options are different from On-premises or previous Privilege Manager Cloud (10.7.x) releases:

* The ServiceNow connector is automatically installed for all new cloud instances.
* The SMTP server is automatically configured during the cloud instance setup.
* The setup is managed by Thycotic and installations, upgrades, and repairs are unavailable to the customer directly, this includes setup, add/remove feature options, and connection options to existing Secret Server. Upgrade notices and banners are removed with upgrades being handled by Thycotic during maintenance periods.
* All license key management is done via Thycotic and license keys are not visible on the licensing page. There are presently no options for customers to add additional licenses directly.

The following features and options are __not__ available in Privilege Manager Cloud:

* Server-side Powershell scripts not signed by Thycotic are not allowed. Custom server-side work can be done via Professional Services engagements.

All other features and functionality of Privilege Manager On-premises and Cloud are the same unless otherwise specified.

## Rollout Recommendation

Familiarize yourself with the [Least Privilege](../../pm-intro/least-privilege.md) concept. Thycotic recommends a phased roll-out between the Application Control and Local Security, for example:

1. [Application Control](../../policy-events/bp-event-discovery.md): Set up learning mode policies on a group of test endpoints to learn about applications running on your endpoint machines ([Event Discovery | Learning Mode Policies – Send Policy Feedback](../../computer-groups/app-control/ac-event-discovery.md))
1. Local Security: Begin [managing your local user accounts](../../computer-groups/local-security/index.md) (only) and defining local group membership (Local Security | Manage Local Users)
1. Application Control: Tailor your policies so that they won't disrupt employee work ([Creating Policies | Elevation Policies](../../computer-groups/app-control/examples/elevate/index.md)) but will block known malicious applications (Creating Policies | Example: Quarantine Specified Malware). Implement these basic policies across agents in production
1. Application Control: Continue to tailor policies according to employee roles. Create a "Request Access" system for any unknown applications. ([Creating Policies | Example: Application Execution Requires Approval](../../computer-groups/app-control/examples/elevate/app-req-app.md) (Workflow))
1. Local Security: Once a workflow has been established between employees and the Privilege Manager Helpdesk, begin managing all local privileged accounts (ex: local admins) on endpoints. (Local Security | Details Tab)

## Local Security

Refer to the Local Security documentation pages to learn more about:

* [Create & Manage Computer Groups, Local Groups, and Users](../../computer-groups/local-security/index.md)

## Application Control

Refer to the Application Control documentation pages to learn more about:

* [Application Control - Policy & Config Overview / Collecting File Data](../../computer-groups/app-control/policies/index.md)
* [Sending Policies to Endpoints - View Deployment Status / Update Using Powershell / Agent Event Log Viewer](../../computer-groups/app-control/ac-policy-endpoints.md)
* [Event Discovery - Learning Mode Policies & Examples / View Policy Results](../../computer-groups/app-control/ac-event-discovery.md)
* [Creating Policies - Allowlisting, Denylisting, Quarantine, Elevation, Greylisting, & Reputation Checking Examples](../../computer-groups/app-control/examples/index.md)
* [Policy Priority Overview & Example](../../computer-groups/app-control/policies/priority.md)

## Integrations

Refer to the Integration documentation pages to learn more about:

* [Integration & Foreign Systems](../../admin/config/foreign-systems/index.md)

## Reports & Troubleshooting

Refer to these documentation pages to learn more about:

* [Reports](../../reports/index.md)
* [Troubleshooting](../../troubleshooting/index.md)

## Catalogs & Reference Guides

Refer to these documentation pages to learn more about:

* [Policies Catalog](../../computer-groups/app-control/policies/index.md)
* [Filters Catalog](../../admin/filters/index.md)
* [Actions Catalog](../../admin/actions/index.md)
* [Privilege Manager Glossary](../../pm-intro/glossary.md)
