[title]: # (Elevation Policies)
[tags]: # (elevate)
[priority]: # (3)
# Elevation Policies

Distinct from Whitelisting policies where applications are simply allowed to run with default user level privileges, an Elevation Policy will apply Administrator credentials to specified applications. This type of policy is often paired with Whitelisting to save IT Administrators time when many employees must perform trusted tasks that require Administrator credentials to complete, like installing a trusted application (Adobe) or device (printer).

In Privilege Manager 10.7 the [Restrict File Dialogs](../../../actions/default-actions.md#Restrict_File_Dialogs) action has been added to the product. Thycotic recommends using this action on elevation policies to prevent the misuse of file open and save dialogs for elevated applications.

Topics in this section:

* [Elevate Applications launched from Network Share Policy](elevation-network-share.md)
* [Elevate Applications whose Execution Requires Approval](elevation-app-req-app.md)
* [Elevate Applications that Require User Justification](elevation-user-just.md)
* [Enable Users to Delete Desktop Application Shortcuts](elevation-delete-shortcut.md)
