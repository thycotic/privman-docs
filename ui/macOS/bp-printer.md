[title]: # (Printers)
[tags]: # (system preferences)
[priority]: # (3)
# Best Practices Printer Installs

To install and manage printers, standard users on macOS systems should be added as members of the __lpadmin__ group.

On macOS system adding a printer can happen in three ways. Two of those can be allowed through an elevation policy enabling a user to add a printer via

* an .app installation file directly or
* a.pkg driver installation directly.

The third option is where the printer setup itself is an application and not an installer. Under that scenario the setup always prompts for admin credentials before the printer can be added.

Also refer to https://support.apple.com/guide/mac-help/add-a-printer-on-mac-mh14004/10.15/mac/10.15 for the latest printer setup information from Apple.
