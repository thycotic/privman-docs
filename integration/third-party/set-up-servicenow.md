[title]: # (Set-up ServiceNow Integration)
[tags]: # (integration)
[priority]: # (9102)
# Set-up ServiceNow Integration

Here are the steps to integrate Workflow between your ServiceNow Ticketing System and Privilege Manager.

1. Verify which ServiceNow User account you will use for your integration with Privilege Manager. If you decide to create a new User account to manage your approval requests, make sure that it includes the roles: Web Service Admin and Approval Admin
1. Verify that the ServiceNow connector is installed for your Privilege Manager Cloud instance:
   1. In the Privilege Manager console navigate to __Admin | Configuration__ and select the __Foreign Systems__ tab.
   1. If the connector is installed, __ServiceNow__ is listed under Foreign System.

      ![Adding ServiceNow as a Foreign System](images/servicenow/fs_servicenow.png)

      If you are a cloud customer and don’t see ServiceNow in the list, contact Thycotic support to have the connector added to your cloud instance. If it is listed, continue with the next step.
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

   ![Approval Request (with ServiceNow Request ItemNumber) Form Action](images/new_req_from_action.png)
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
