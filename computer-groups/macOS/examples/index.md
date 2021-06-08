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

| Actions | pre Catalina & Catalina with __KEXT__ | Catalina & Big Sur or later with __SYSEX__ |
| ----- | -----| ----- |
| Allow Copy to /Applications Directory | supported | A privileged helper that uses an authorization right can be used. This needs to happen by an AuthorizationDB Right action. |
| Allow Package Installation | elevate via UI | via `sudo` plugin |
| Application Approval Request (with Offline Fallback) Message Action | elevate via UI | via `sudo` plugin |
| Application Approval Request (with ServiceNow Request Item Number) Message Action | elevate via UI | via `sudo` plugin |
| Application Approval Request Message Action (workflow request) | elevate via UI | via `sudo` plugin |
| Application Denied Message Action | no difference | no difference |
| Application Justification Message Action | elevate via UI | via `sudo` plugin |
| Application Warning Message Action | no difference | no difference |
| Deny Execute / Deny Execute Message | no difference | no difference |
| File Quarantine | no difference | no difference |
| Quarantine Message | no difference | no difference |
| Run as Root (Elevate) | no difference | via `sudo` plugin |
| Just In Time (Elevate) | n/a | via `sudo` plugin |

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
