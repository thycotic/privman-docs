[title]: # (Best Practices)
[tags]: # (system preferences)
[priority]: # (2)
# Best Practices System Preferences

On macOS systems, users (Admin and Standard) can customize the System Preferences based on their macOS role scope. Details about macOS based customizations via the system preferences can be found at https://support.apple.com/guide/mac-help/change-system-preferences-mh15217/mac.

With Privilege Manager you can implement policies that provide application control to deny execution of all preference panes. Run as root policies are only supported and recommended for management of the following preference panes:

* [Date & Time](bp-date-time.md)
* [Energy Saver](bp-energy-saver.md)
* [Network](bp-network.md)

The following rules apply for policy managed preference panes:

* If we have no policy for a given preference pane, the authorization for it is left to its system default.
* A preference pane's default authorization is restored when a policy for it is disabled/deleted.
* Managed preference pane defaults are restored on an uninstall.

>**Note**: For preference panes that display the padlock icon, if you click the padlock to close it, you are required to enter admin credentials to unlock it again. Due to the way macOS caches preference pane authorizations, if a standard user has clicked the padlock icon, they will have to close and reopen System Preferences for the policy evaluation to be performed again.

## Error Behavior of Preference Panes

When a particular preference pane is opened in the System Preferences application, XPC bundles for that particular preference pane are opened. These XPC bundles remain open until the System Preferences application is completely closed.

This behavior can result in apparent failed policy evaluations. Opening a preference pane that has previously been opened and evaluated without closing the System Preferences application following the initial opening, results in the policy evaluation not triggering again for that particular preference pane due to the XPC bundle remaining open.

For example, if you have a policy that requires approval of Date & Time preference pane changes and our notification dialog is cancelled and then Date & Time is opened again, our notification dialog is not presented to the user again. Instead, a sheet dialog indicates that the preference pane can't be loaded. In order to trigger policy evaluation again, System Preferences must be closed and then reopened.

## User Based Behavior of Preference Panes

### Standard User

Without an active policy, preference panes appear locked and standard users are not able to make changes. The exception is the Date & Time preference pane. Standard users are allowed to edit the clock appearance. Any changes here are specific to the user's session and can be modified without clicking the locked padlock icon despite what the text next to the icon says.

With an active policy, depending on its action, the following happens for:

* __Deny Execute__ | __Deny Execute Message__ | __Application Denied__ - The user is presented with a dialog indicating they are denied running the preference pane. Depending on the usage of Deny Execute Message versus Application Denied Message and the version of macOS, each one may appear twice.
* __Application Justification__ - The user is presented with the justification dialog. Once the user enters a justification and clicks Continue, all controls on the pane are enabled. Any changes made are saved. When the user clicks Cancel, macOS will display an error sheet in System Preferences indicating there was an error loading the preference pane.
* __Application Warning__ - The user is presented with the warning dialog. When the user clicks Cancel, macOS will display an error sheet in System Preferences indicating there was an error loading the preference pane. When the user clicks Continue, all controls on the pane are enabled and any changes made are saved.
* __Application Approval Request__ - The user should be presented with the approval dialog. When the user clicks Cancel, macOS will display an error sheet in System Preferences indicating there was an error loading the preference pane. Once the user enters a reason and clicks Continue, the dialog for waiting for approval is displayed. If the user clicks Cancel in the waiting dialog, macOS will display an error sheet in System Preferences indicating there was an error loading the preference pane. Depending on the Approval action (Allow or Deny), the following takes place:
  * __Allow__ - All controls on the pane are enabled. Any changes made are saved.
  * __Deny__ - macOS will display an error sheet in System Preferences indicating there was an error loading the preference pane.

The following preference panes require admin credentials to make changes and should not be managed with a run as root policy that triggers a user dialog for justification or approvals:

* Parental Controls,
* [Printers & Scanners](bp-printers.md),
* Security & Privacy,
* Sharing,
* Time Machine, and
* Users & Groups

### Admin User

Local admin users should not be managed by any policies requiring user interaction when the policy is triggered. For macOS endpoints the only type of policy would be to demote administrative rights for a particular preference pane by simply denying access.
