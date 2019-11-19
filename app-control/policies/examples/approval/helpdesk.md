[title]: # (Help Desk Approvals)
[tags]: # (elevation request)
[priority]: # (3)
# Help Desk Approvals

# Elevation Requests

Application Control Solution (ACS) enables end users to request elevation and then have their request approved or denied by the help desk. You can approve or deny requests via the Thycotic Management Server (TMS), or forward requests to a third-party ticketing system such as:

* LANDESK Service Desk
* Microsoft SharePoint
* ServiceNow

## Enable elevation requests
To enable elevation requests in ACS, do the following steps:

1. In the Thycotic Security Manager, click the Policies tab.
1. In the file library in the left pane, navigate to Application Control | Policies | Privilege Management | User Requested MSI Elevation Justification Policy.
1. In the policy settings in the right pane, click the red Off button to enable the policy. Click the Application Actions tab.
1. Under Applications, select Applications action (the default action is Approval Request Form Action or you can create a new request message for a third-party integration).
1. Click Apply To and apply the policy to targeted computers.
1. Click Save.

After you save the policy and the agent receives the update, the new message looks like this:

<!-- TODO update image -->

Users will enter their written request in the Reason (required) field and then send the request to the AMS.

For the default manual approval process you can use the Security Manager Console and Help Desk Console to approve or deny requests. For more complex approval options see Approval Requests.

## End users
When end users try to open a restricted application, they must enter a reason for needing the application and send it for approval:

While the request is being evaluated, whenever end users start the application they have requested elevation for, a status pending message will appear:

After the request has been approved or denied, then end users will receive the approval or denial message:

## Approve requests
To approve or deny requests in the Security Manager Console, go to Application Execution Requests to view all application requests:

To approve or deny requests in the Help Desk Console, click the Approve Requests tab:

## What's covered

* Disclose passwords
* Approve requests
* Reports

To access the Thycotic Help Desk Console, type the following URL into your web browser: https://{your server name}/AMS/HelpDesk.

The Help Desk Console is an area where employees who do not have full access to the Security Manager Console can perform their job functions, such as viewing and disclosing passwords, and responding to various requests.

For details about giving specific users access to the Help Desk see Giving Help Desk Users Access to Arellia. <!-- shouldn't this be changed to Privilege Manager for all instances on this page? -->

The Help Desk Console includes the following tabs, which appear along the top of the screen:

### Disclose Passwords

If the Arellia Local Security Solution is installed, then the Disclose Passwords tab will appear. In this area you can select a computer, view its managed passwords, and disclose those passwords. To see the process for viewing a password in the Help Desk Console, go to Disclosing Randomized Passwords via the Help Desk View.

### Approve Requests

In the Approve Requests tab you can approve or deny various requests. This tab is available with the default console configuration, but the available options will vary depending on which Arellia solutions are installed. Different Thycotic solutions have different request types. To learn more about responding to requests, go to Request Elevation.

### Reports

The Reports tab will be empty until reports are added to the Helpdesk Reports folder in the Security Manager Console. In this way, Administrators can make specific reports available to employees who do not have full access to all reporting.
