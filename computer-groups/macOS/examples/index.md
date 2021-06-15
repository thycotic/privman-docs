[title]: # (macOS Specific Policies)
[tags]: # (policy examples)
[priority]: # (6)
# macOS Specific Policies

Once your macOS agent is registered, creating policies for your macOS machines follows a very similar process to creating policies for Windows machines in Privilege Manager. The main approach should be via the use of the Policy Wizard aided by the following:

1. Collect File Data — This enables Privilege Manager to recognize specific files and file types in your environment. The file data that you want to target with policies are called Events. All imported files can be viewed via __File Inventory__.
1. Create Filters — This step sorts important file data (Events) according to different criteria.
1. Create Policies — This step defines what
   1. Actions to perform on applications and
   1. Targets (Locations) for those actions.
1. Assign Filters to Policies — This step directs a Policy's actions to the appropriate Events happening on your network. This step also allows a Policy to be set to active.
1. Order your Policies based on priority level—Once your policies are created, the order they execute across your network matters. See the [Policy Priority](../../app-control/policies/priority.md) topic for more details.

In macOS, roles are bifurcated into two groups: Admins, and Users rather than by Group Policy Objects (GPO) found in Windows environments.

## Actions Supported by macOS Agents (Kernel vs System Extensions)

The following actions are supported by macOS agents:

| Action | KEXT | SYSEX | Versions | Usage |
| ----- | ----- | ----- | ----- | ----- |
| Allow Copy to /Applications/ Directory | Y | Y | 10.5+ | Used to elevate installation of an Application Bundle to the /Applications folder via Drag-n-Drop to the Privilege Manager.app window. This is legacy and will be deprecated in an upcoming release. |
| Allow Package Installation | Y | Y | 10.5+ | Used to elevate installation of installer packages.  |
| Application Approval Request (with Offline Fallback) Message Action| Y | Y | 10.6+ | |
| Application Approval Request (with ServiceNow Request Item Number) Message Action | Y | Y | 10.5+ | |
| ​Application Approval Request Message Action| Y | Y | 10.5+ | |
| Application Denied Message Action| Y | Y | 10.5+ | |
| Application Justification Message Action| Y | Y | 10.5+ | |
| Application Warning Message Action  | Y | Y | 10.5+ | |
| Authorization DB Rights | N | Y | 11.0+ | Grants the specified right allowing an application to perform an elevated task. |
| Command Line Approval Message | N | Y | 11.1+ | |
| Command Line Justification Question | N | Y | 11.1+ | |
| Deny Execute| Y | Y | 10.5+ | |
| Deny Execute Message | Y | Y | 10.5+ | |
| Display User Message | Y | Y | 10.5+ | |
| File Quarantine| Y | Y | 10.5+ | |
| Just in Time Group Membership | N | Y | 10.8.2+  | |
| Run as Custom User| Y | N | 10.5-10.8.2 | |
| Run as Print Admin User | Y | N | 10.5-10.8.2 | |
| Run as Root | Y | N | 10.5-10.8.2 | |
| Run As User | N | Y | 11.1+ | |

The following actions are specific to the use of sudo through our sudo plugin:

* [Command Line Approval Message](../../../admin/actions/macOS/cli-appr-msg.md)
* [Command Line Justification Message](../../../admin/actions/macOS/cli-just-msg.md)
* [Run As User](../../../admin/actions/macOS/run-as-user.md)

### Agent Behavior with Actions

When a policy is used to manage .pkg installations on macOS endpoints with the Privilege Manager agent installed, you can expect the following behaviors:

Installation of a .pkg happens without prompting for credentials when

* the only action configured in the policy is __Allow Package Installation__ or
* if any of the following are configured along with __Allow Package Installation__:
  * Application Approval Request Message Action
  * Application Approval Request (with Offline Fallback) Message Action
  * Approval Request (with ServiceNow Request Item Number) Form Action
  * Application Justification Message Action
  * Application Warning Message Action

A .pkg will NOT be installed if the only action is either of the following:

* Deny Execute
* Deny Execute + Deny Execute Message
* Application Denied Message Action

Any .pkg not managed by a Privilege Manager policy will be installed via the normal macOS workflow requiring admin credentials when prompted.
