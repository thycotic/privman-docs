[title]: # (Elevation Policies)
[tags]: # (elevate)
[priority]: # (3)
# Elevation Policies

Distinct from allow policies where applications are simply allowed to run with default user level privileges, an Elevation Policy will apply Administrator credentials to specified applications. This type of policy is often paired with allowlisting to save IT Administrators time when many employees must perform trusted tasks that require Administrator credentials to complete, like installing a trusted application (Adobe) or device (printer).

In Privilege Manager 10.7 the [Restrict File Dialogs](../../../../admin/actions/default-actions.md#Restrict_File_Dialogs) action has been added to the product. Thycotic recommends using this action on elevation policies to prevent the misuse of file open and save dialogs for elevated applications.

Topics in this section:

* [Setting up ActiveX Policies](active-x.md)
* [UAC Override Policy](uac-override.md)
* [Elevating the Privilege Manager Remove Programs Utility Policy](pm-remove-prog.md)
* [Elevate Applications launched from Network Share Policy](network-share.md)
* [Elevate msi launched from a Network Share](msi.md)
* [Elevate Applications whose Execution Requires Approval](app-req-app.md)
* [Elevate Applications that Require User Justification](user-just.md)
* MS Visual Studio Installations - Filters and policy now provided via Configuration Feeds. Refer to [Config Feeds](../../../../admin/config-feeds/index.md) for download and installation information.
