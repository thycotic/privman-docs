[title]: # (ServiceNow)
[tags]: # (integration)
[priority]: # (9102)
# Set-up ServiceNow Integration

Here are the steps to integrate Workflow between your ServiceNow Ticketing System and Privilege Manager.

1. Verify which ServiceNow User account you will use for your integration with Privilege Manager. If you decide to create a new User account to manage your approval requests, make sure that it includes the roles: Web Service Admin and Approval Admin
1. Verify that the ServiceNow connector is installed for your Privilege Manager Cloud instance:
   1. In the Privilege Manager console navigate to __Admin | Configuration__ and select the __Foreign Systems__ tab.
   1. If the connector is installed, __ServiceNow__ is listed under Foreign System.

      ![Adding ServiceNow as a Foreign System](images/servicenow/fs_servicenow.png)

      >**Note**: If you are a 10.6 cloud customer and don’t see ServiceNow in the list, contact Thycotic support to have the connector added to your cloud instance. If it is listed, continue with the next step.
1. Select the __Credentials__ tab.
1. Click __Add New__.
1. Under Details, enter a Name and Description for your ServiceNow credentials.
1. Under Settings, enter the information from your ServiceNow User account that was referenced in step 1 above, click Save.
1. Select the __Foreign Systems__ tab.
1. Select the __ServiceNow__ link from the list of foreign systems displayed.
1. Click __Add New__.
1. Enter a Name for your Service Now Server.
1. Enter the base Uri from your ServiceNow instance

   `https://[InstanceName].service-now.com/`, click __Create__.
1. Select your ServiceNow instance, click __Edit__.
1. Assign the credentials you created to link them to your instance.

   ![Linking the credentials](images/servicenow/fs_link_credentials.png)
1. Next, in __Search__ at the top of your Privilege Manager console, search for _Create ServiceNow Approval Request Items_.
1. In your search results, __click on this task__ and then the __Run Task__ button.

   ![Run task](images/servicenow/task_appr_request_item.png)
1. Under Task Settings, click Select resource and add the ServiceNow Server that you created as a Foreign System in step 10.
1. Click __Run Task__.

   >**Note**:
   >Clients with robust ServiceNow installations are welcome (and in fact encouraged) to alter their ServiceNow scripted web services for use with their own ServiceNow items and workflow rather than relying on this importing task.

   The task you just ran creates several new items in your ServiceNow dashboard.

## ServiceNow Steps

Open ServiceNow and navigate to __Scripted Web Services | Scripted SOAP Services__ to verify that these three new options are listed:

* CancelExecuteAppApprovalRequest,
* CreateExecuteAppApprovalRequest,
* GetExecuteAppApprovalRequestStatus  

  ![Three new ServiceNow Services](images/servicenow/sn_3new.png)

Now you've successfully defined a SOAP endpoint that Privilege Manager knows how to call to initiate a ServiceNow request for approval.

## Define Action and Policy

You need to create an action and attach it to a policy to manage what events you want sent to ServiceNow for approvals. To do this,

1. In the Privilege Manager console, navigate to __Admin | More__ and select __Tasks__.
1. Click the __Automation__ tab.
1. In the tree navigate to __Automation | Approvals | Approval Processes__, click __Add New__.

   ![New Automation](images/servicenow/action_new.png)
1. Enter a name and description, click __Create__.
1. Click __Edit__ on the newly created ServiceNow Approval Process.

   ![Editing the item](images/servicenow/action_addserver.png)
1. Under __Settings__ specify your ServiceNow Server, click __Save__.
1. Back in the Automation tree, select __Approval Types__, click __Edit__ for the default.

   ![Default approval type](images/servicenow/action_type.png)
1. Select your __ServiceNow Approval Process__, click __Save__.

   ![Edits to approval type](images/servicenow/action_type2.png)
1. Now navigate to __Admin | Actions__.
1. Search and select __Approval Request (with ServiceNow Request ItemNumber) Form Action__. 

   ![Approval Request (with ServiceNow Request ItemNumber) Form Action](images/servicenow/new_req_form_action.png)
1. Click __Create a Copy__.
1. Name your new action and click __Create__.
1. Click __Edit__.
1. Customize the Action based on your specific business requirements.
1. Click __Save__.
1. Navigate to __Admin |Policies__, click __Create New__ or find an existing policy that you want to use for ServiceNow Approvals. 
1. Select the __Actions__ tab.
1. Click __Edit__ and __Add Action__.
1. Search for the action you created in step 5, _ServiceNow Approval Request Form Action_, click __Add__.
1. Click __Save__.
1. Select the __Deployment__ tab.
1. Click __Run Policy Targeting Update__ to immediately send the policy to your endpoint agents.

Policies also automatically update according to a schedule.

## Integration Workflow

Now that you have a policy attached to your ServiceNow integrated Action, the requests from your policy will be sent through ServiceNow for approval.

1. On your endpoint, perform the action that your policy targets for ServiceNow Approval. You will be prompted with a justification window to explain your request. To approve these requests, open your ServiceNow Dashboard.
1. Go to __MyApprovals__ in ServiceNow and you will see your new requests.
1. Click Requested for details.
1. In the Request page you will be able to view details of what action is being requested, and you can Accept the action.
1. On your endpoint, the pending justification window will update to an Approved status, and the user will be able to access their requested application.

## Create Approval Request Items Task

Privilege Manager integrates with ServiceNow to manage approvals for user-requested application execution and elevation.  For this integration to work there are several items that must be created in your ServiceNow instance.  You can create these items manually or run the Create ServiceNow Approval Request Items task in Privilege Manager to create them automatically.

Most of the items created automatically by the Create ServiceNow Approval Request Items task are generic, and you are encouraged to replace these items with their own, and use your own workflows, forms, etc.  This document describes what default items this task creates, and what is required for the integration to work so that you can adjust according to your own ServiceNow system.

## How to create ServiceNow Approval Request Items Task

When you run the Create ServiceNow Approval Request Items task, Privilege Manager creates the necessary items in ServiceNow so that it can use ServiceNow to manage requests to approve execution or elevation of applications.  This section describes each item and their functions:

__Thycotic__:

The task creates a service catalog category named “Thycotic” within your ServiceNow UI.

__Execute Application Request__:

The task creates a service catalog item named “Execute Application Request” and associates it with the Thycotic service catalog category.

## Variables

| Variables | Description  |
| ----- | ----- |
| PMApprovalId | The Privilege Manager internal identifier for the approval request |
| PMInitiatorId | The Privilege Manager internal identifier for the user that initiated the request |
| PMInitiatorName | The name of the user that initiated the request |
| PMPolicyId | The Privilege Manager internal identifier for the policy associated with the approval request |
| PMPolicyName | The name of the policy associated with the approval request |
| PMAgentId | The Privilege Manager internal identifier for the endpoint on which the request was initiated |
| PMAgentName | The name of the endpoint on which the request was initiated |
| PMProcessId | The Privilege Manager internal identifier for the process configuration item associated with the approval request |
| PMProcessName | The name of the process configuration item associated with the approval request |
| PMFilePath | The path to the application the user is attempting to run |
| PMUserReason | The reason given by the user requesting the approval |

### CreateExecuteAppApprovalRequest

The task creates a scripted SOAP service named “CreateExecuteAppApprovalRequest.” When a user initiates an approval request, Privilege Manager will call this service with input data about the request.  The default script will create a new Execute Application Request service catalog item, fill out the variable data from the inputs, and submit the item. The service returns the ID of the item to Privilege Manager so that it can periodically check or update the status of the item.

### Script Input

The task creates inputs with the same names as the Variables in Execute Application Request listed above

### Script Output

The task creates an output named “PMRequestId.”  Privilege Manager looks for this output by name and records it so can be used in future service calls to check or update the request status.

### GetExecuteAppApprovalRequestStatus

The task creates scripted SOAP service named “GetExecuteAppApprovalRequestStatus.”  When an approval is in progress, Privilege Manager will periodically call this service to determine if the request has been approved or rejected.

### Script Input

The task creates an input named “PMGetRequestId.”  Privilege Manager supplies this input using the value from PMRequestId that was output from the CreateExecuteAppApprovalRequest service.

### Script Output

| Script Output | Description |
| ----- | ----- |
| PMApprovalStatus | Privilege Manager expects this service to return PMApprovalStatus with one of the following values:|
|   | approved: The request has been approved |
|   | rejected: The request has been rejected |
|   | pending: The request is still pending approval or rejection |
|   | invalid: PMGetRequestId is not a valid ID, or the approval request is in an otherwise invalid state and will be rejected by Privilege Manager.
| PMComment | If there is a comment by the worker that approved or rejected the request, it can optionally be returned in the output named PMComment.  If this output is present Privilege Manager will record it with the status of the request in its database |

### CancelExecuteAppApprovalRequest

The task creates a scripted SOAP service named “CancelExecuteAppApprovalRequest.”  If a request is canceled or times out from within Privilege Manager, Privilege Manger will call this service to cancel the corresponding item in ServiceNow.

>**NOTE**: Privilege Manager expects this service to be defined in ServiceNow, but the default script associated with the service does nothing.

### Inputs

| Inputs | |
| ----- | ----- |
| PMCancelRequestId |  Privilege Manager call this service with PMCancelRequestId set to the value from PMRequestId returned from the CreateExecuteAppApprovalRequest service. |
| PMCancelComment | Privilege Manager calls this service with PMCancelComment set to a comment about why the request is being canceled. |

### Outputs

The task creates the output named __TmsCancelResult__.  Privilege Manager expects an output with this name, but currently ignores the value.

## Required Integration Points

### What Can Change vs. What Must Remain

Most of the ServiceNow back end can be changed to accommodate your own items and workflows.  Privilege Manager only requires the three scripted SOAP web services described above.  You are welcome to change the script within the services to do whatever is necessary for your environment.  

While the inputs that Privilege Manager sends to the services are fixed, once they reach ServiceNow you are free to do (or not do) what you want with the values.

Privilege Manager expects the outputs from the services as described above.  PMRequestId is by default the ServiceNow sys_id of the requested service catalog item instance, but can be any string up to 256 characters used to identify the request.  It’s up to you to ensure that the status and cancel services can interpret that value.

You can change the names of the services if you update the names in the ServiceNow Approval Process configuration in Privilege Manager.  You can also create multiple ServiceNow Approval Process items within Privilege Manager, and each can reference their own set of services.
