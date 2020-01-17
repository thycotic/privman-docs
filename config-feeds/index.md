[title]: # (Configuration Feeds)
[tags]: # (overview)
[priority]: # (8000)
# Configuration Feeds

Configuration Feeds are extensions to Privilege Manager. They can be found by navigating to __Admin | More__ and then selecting the __Config Feed__ link. 
Configuration feeds allow Thycotic to deliver new components/items to Privilege Manager. Simply click through the options in the Config Feeds page starting with the Select Items button and download anything that might be useful in your environment. Once the item is downloaded, it is immediately available in your Privilege Manager instance.

The main product areas covered are:

* Application Control Solution
* Local Security Solution
* Thycotic Management Server Core

| Solution | Feed | Description |
| ----- | ----- | ----- |
| Application Control Solution| [Ignoring macOS Updates](../config-feeds\ignore-os-updates.md) |Contains the policy to ignore macOS Catalina in the Software Update preference pane.
| |[Reset ignored macOS Software Updates](../config-feeds\ignore-os-updates.md) |Contains the policy to reset ignored macOS software updates in the Software Update preference pane.
| | AP - Remove Programs Helper | Contains the policies for the Remove Programs Helper Utility. **Note**: This only pertains to Privilege Manager versions prior to 10.7. In 10.7 and up, the [utility is automatically installed](../how-to/maintenance/remove-programs-utility.md) and can be [enabled via policy](../app-control/policies/examples/elevate/pm-remove-prog.md).|
| | [AP - UNC Elevation Policy Template](../app-control/policies/examples/elevate/network-share.md) | Contains the UNC Share Elevation Policy Template to scan a network share and automatically elevate MSI and EXE files. |
| | AP - UNC Whitelist Policy Template | Contains the UNC Share Whitelist Policy Template to scan a network share and automatically whitelist files in MSI, ISO, ZIP files. |
| | Browser Lockdown | Contains Configurable Browser Lockdown Settings. |
| | [Secondary File Hash Exclusion Policy](exclude-from-file-hash.md) | Policy template to exclude non-executable files from the hash process. |
| Local Security Solution | Local Security Solution - Disclose Password HelpDesk Tab | Adds the helpdesk tab to the Security Manager console. |
| Thycotic Management Server Core | Maintenance Resources | Contains maintenance gauges, tasks, etc. for optimal TMS performance. |
| | OU Based Computer Groups | Contains a task to automatically create OU based computers groups and collections. |
| | SQL CPU Usage Gauge | Contains a gauge and report to monitor SQL CPU usage. |
| | Windows Server and Desktop Filters | Contains Windows Server and Desktop Filters. |
