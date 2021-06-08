[title]: # (Printers)
[tags]: # (system preferences)
[priority]: # (3)
# Best Practices Printer Installs

To install and manage printers via the Printers and Scanners preference pane, standard users on macOS should be added as members of the __lpadmin__ group. You can use Privilege Manager's [LSS user and group management features](../../../computer-groups/local-security/u-mgmt/index.md) to assist with this.

On macOS, adding a printer can happen in three ways. Two of those can be allowed through an elevation policy enabling a user to add a printer via

* an .app installation file directly or
* a .pkg driver installation directly.

The third option is where the Printers and Scanners preference pane is used to manually add a printer based on existing printer drivers. Refer to the link below for more information.

Under the first scenario, the application that is performing the install and configuration of the printer may prompt for admin credentials. If this is the case, you may need a policy that allows the application or applications provider by the printer vendor.

Refer to https://support.apple.com/guide/mac-help/add-a-printer-on-mac-mh14004/10.15/mac/10.15 for the latest printer setup information from Apple.
