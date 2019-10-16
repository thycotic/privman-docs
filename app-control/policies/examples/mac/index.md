[title]: # (macOS Specific Policies)
[tags]: # ( )
[priority]: # (6)
# macOS Specific Policies

Once your macOS agent is registered, creating policies for your macOS machines follows a very similar process to creating policies for Windows machines in Privilege Manager:

1. Collect File Data—This enables Privilege Manager to recognize specific files and file types in your environment. The file data that you want to target with policies are called Events. All imported files can be viewed in the Event Discovery | Files page.
1. Create Filters—This step sorts important file data (Events) according to different criteria.
1. Create Policies—This step defines what 1) Actions to perform on applications and the 2) Targets (Locations) for those actions.
1. Assign Filters to Policies—This step directs a Policy’s actions to the appropriate Events happening on your network. This step also allows a Policy to be Enabled, or activated.
1. Order your Policies based on priority level—Once your policies are created, the order they execute across your network matters. See the Policy Priority section in this guide for more details.

In macOS, roles are bifurcated into two groups: Admins, and Users rather than by Group Policy Objects (GPO) found in Windows environments.

## Actions supported by macOS Agents

The following actions are supported by macOS agents:

* Allow Copy to /Applications/Directory
* Allow Package Installation
* Application Approval Request (with Offline Fallback) Message Action
* Application Approval Request (with ServiceNow Request Item Number) Message Action
* Application Approval Request Message Action (workflow request)
* Application Denied Message Action
* Application Justification Message Action
* Application Warning Message Action
* Deny Execute / Deny Execute Message
* File Quarantine
* Quarantine Message
* Run as Root (Elevate)

The following macOS specific policy examples are available:

* [Allow Copy/Install of Applications](copy-install.md)
* [Request Application Installation](app-install-approval-request.md)
* [Application Self-elevation](self-elevation.md)
* [Use Discovery to Determine if an Application Requires Admin Privileges](determ-admin.md)
* [Require Justification for Firefox](justification-firefox.md)
