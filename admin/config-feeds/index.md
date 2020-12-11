[title]: # (Configuration Feeds)
[tags]: # (adding templates,out-of-the-box)
[priority]: # (2)
# Configuration Feeds

Configuration Feeds are extensions to Privilege Manager. They can be found by navigating to __Admin | More__ and then selecting the __Config Feed__ link. 
Configuration feeds allow Thycotic to deliver new components/items to Privilege Manager. Simply click through the options in the Config Feeds page starting with the Select Items button and download anything that might be useful in your environment. Once the item is downloaded, it is immediately available in your Privilege Manager instance.

The main product areas covered are:

* Application Control Solution
* Local Security Solution
* Thycotic Management Server Core

| Solution | Feed | Description |
| ----- | ----- | ----- |
| Application Control Solution | [Ignoring macOS Updates](../config-feeds/ignore-os-updates.md) |Contains the policy to ignore macOS Catalina in the Software Update preference pane.
| |[Reset ignored macOS Software Updates](../config-feeds/ignore-os-updates.md) |Contains the policy to reset ignored macOS software updates in the Software Update preference pane.
| | [Secondary File Hash Exclusion Policy](exclude-from-file-hash.md) | Policy template to exclude non-executable files from the hash process. |
| | UNC Allow Policy Template | Contains the UNC Share Allow Policy Template to scan a network share and automatically allow files in MSI, ISO, ZIP files. |
| | [UNC Elevation Policy Template](../../computer-groups/app-control/examples/elevate/network-share.md) | Contains the UNC Share Elevation Policy Template to scan a network share and automatically elevate MSI and EXE files. |
| | Visual Studio Installer Elevation | This configuration feed imports example filters and a policy for elevating Visual Studio Installers. After the installation the policy needs to be activated. |
| Local Security Solution |  Disclose Password HelpDesk Tab | Adds the helpdesk tab to the Security Manager console. |
| Thycotic Management Server Core | Maintenance Resources | Contains maintenance gauges, tasks, etc. for optimal TMS performance. |
| | [Reset Agent Service Permissions](../../agents/win/pre-10.7.1-agent-hardening.md) | Contains a policy to restore the security descriptor on Thycotic Services for Privilege Manager versions prior to 10.7.1. |
| | SQL CPU Usage Gauge | Contains a gauge and report to monitor SQL CPU usage. |
| | [Privileged Behavior Analytics Integration](../config/foreign-systems/thycotic/set-up-pba.md) | Contains tasks for sending data to Privileged Behavior Analytics (PBA) - requires a SysLog Foreign System to be configured. |
