[title]: # (Help Desk Approvals)
[tags]: # (elevation request)
[priority]: # (3)
# Help Desk Approvals

Privilege Manager enables end users to request elevation and then have their request approved or denied by the helpdesk. You can approve or deny requests via the Privilege Manager console, or forward requests to a third-party ticketing system such as ServiceNow.

## Creating a Helpdesk Policy

1. Navigate to __ADMIN | Policies__.
1. Click __Add New Policy__.
1. From the Platform drop-down select __Windows__.
1. From the Policy Type drop-down select __Elevate Application Privileges__.
1. Name the policy, in our example we changed New to Helpdesk.
1. From the Action drop-down select __Require Approval__.

   ![Add new policy](images\help-desk\helpdesk-1.png) "Create new Helpdesk approval policy")
1. Click __Create__.

   ![Helpdesk policy](images\help-desk\helpdesk-2.png "Helpdesk policy general tab")
1. Click __Edit__.
1. Navigate to the __Conditions__ tab and add any applications that you want to target with this policy.

   ![Conditions tab](images\help-desk\helpdesk-3.png "Conditions tab - add target applications")

   1. Click on the __+__ to add an Application Target.
   1. Click __Add__.
1. Navigate to the __Actions__ tab. Verify the following actions are listed

   * __Approval Request From Action__
   * __Restrict File Dialogs__
   * __Add Administrative Rights__.

   ![Actions tab](images\help-desk\helpdesk-4.png "Actions tab - verify actions to be taken")
1. On the General tab, select the Enable checkbox.
1. Click __Save__.

Once the agent receives the update, users receive a message action dialog to enter their written request in the Reason (required) field which then sends a request to either the Privilege Manager console or integrated Helpdesk.

## Workflow

When end users try to open a restricted application, they must enter a reason for needing the application and send it for approval. While the request is being evaluated, whenever end users start the application a status pending message will appear. Once the request has been approved or denied, end users receive an approval or denial.

## Approve requests

To approve or deny requests in the Privilege Manager Console, go to __TOOLS | Manage Approvals__ to view all application requests.
