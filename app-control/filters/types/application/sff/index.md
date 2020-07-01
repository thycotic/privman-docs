[title]: # (Secondary File)
[tags]: # (policy, deny, allow, best practice)
[priority]: # (2)
# Using Secondary File Filters

This topic explains how to create policies for applications that trigger file executions. Implementing a policy to filter on a file type, which is used by another executable, is done by setting a __Secondary File Filter__. The Secondary File Filter is available for both Windows and macOS systems.

The following topics show the steps to create policies and include filters that enforce actions on endpoints when batch files, PowerShell scripts, or Microsoft Installer files execute. Any type of executer can be specified and policed this way.

In general, the steps are similar for the different file types to be policed.

## Via File Inventory

* With Learning Mode enabled, you use the File Inventory to discover new resources.
* Select a discovered resource and use __Create Filter__.
* On the Manage Application modal select which specifications to match.
* Use __Create and Add to Policy__ option.

## Via Policy Wizard

* You create a controlling policy via the Wizard.
* On the __What do you want to target step?__ you can select an existing filter, upload a file (recommended for .msi/.exe applications), or use an already inventoried file.
* Policy Wizard builds the policy and after you name and create it, you can further customize all the details. The Policy wizard automatically adds the correct application targets, inclusions an/or exclusions.

## Examples

* [Best Practices](secondaryfilefilters.md)
* [Targeting script file execution, like .bat and .ps1](batch.md)
* [Targeting installer/executables execution, like .msi and .exe](msi.md)
