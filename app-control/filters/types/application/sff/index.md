[title]: # (Secondary File)
[tags]: # (policy, deny, allow, best practice)
[priority]: # (2)
# Using Secondary File Filters

This topic explains how to create policies for applications that trigger file executions. Implementing a policy to filter on a file type, which is used by another executable, is done by setting a __Secondary File Filter__. The Secondary File Filter is available for both Windows and macOS systems.

This following topics show the steps used to create filters and policies that enforce actions on endpoints when batch files, PowerShell scripts, or Microsoft Installer files execute. Any type of executer can be specified and policed this way.

In general, the steps are similar for the different file types to be policed.

## Via File Inventory (automatic)

* With Learning Mode enabled, you use the File Inventory to discover new resources.
* Select a discovered resource and use __Create Filter__.
* On the Manage Application modal select which specifications to match.
* Use __Create and Add to Policy__ option.

## Manually

* You first create an application or file filter that identifies the executing application, for example `*.ps1`,
* then you create the secondary file filter identifying the file type by adding the file or application filter (`*.ps1`) under __Settings__,
* then you create a policy, specifying Application Targets, and
* use an Inclusion and/or Exclusion filter specified as and using the Secondary File Filter.

## Examples

* [Best Practices](bp-sff.md)
* [Targeting Batch file execution](batch.md)
* [Targeting PowerShell script execution](ps1.md)
* [Targeting MSI execution](msi.md)
