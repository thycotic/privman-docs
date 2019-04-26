[title]: # (Set-up ServiceNow Integration)
[tags]: # (integration)
[priority]: # (112)
# Set-up ServiceNow Integration

1. Verify which ServiceNow User account you will use for your integration with Privilege Manager. If you decide to create a new User account to manage your approval requests, make sure that it includes the roles: Web Service Admin and Approval Admin
1. Navigate to your Thycotic Management Server Setup page at https://DomainName/TMS/Setup/ProductOptions/ShowProducts.
1. Install the Thycotic ServiceNow Connector add-on and the Thycotic Management Server Silverlight Console.

​   User-added image

1. Navigate back to Privilege Manager's Dashboard (https://DomainName/TMS/PrivilegeManager) and then Admin | Configuration | User Credentials tab

​   User-added image

1. Create a new User Credential by clicking the +User Credential icon above the table, click into your New User Credential and Edit the Name (ServiceNow) and add a Description. Under Settings, provide the ServiceNow Account Name and Password that you will use to run this integration and Approval Management (Step 1). Click Save, then Back.
1. Next, under Configuration select the Foreign Systems tab. Click ServiceNow, then Add New. Add a Name (ServiceNow Server) and the Base Uri from your ServiceNow instance. Click Create.

​   User-added image
   User-added image

1. Next, in the Search Bar at the top of your Privilege Manager screen, search for "Create ServiceNow Approval Request Items" In your search results, click on this task and then the Run Task button. Under Task Settings, click Select resource and add the ServiceNow Server that you created as a Foreign System in step 6. Then click Run Task.
​
   > **Note**: Clients with robust ServiceNow installations are welcome (and in fact encouraged) to alter their ServiceNow scripted web services for use with their own ServiceNow items and workflow rather than relying on this importing task. For more information on this, see our Advanced ServiceNow Integration Guide here.

   User-added image
   User-added image

1. The task you just ran creates several new items in your ServiceNow dashboard. Open ServiceNow and navigate to Scripted Web Services | Scripted SOAP Services to verify that these three new options are listed:
   1) CancelExecuteAppApprovalRequest,
   2) CreateExecuteAppApprovalRequest,
   3) GetExecuteAppApprovalRequestStatus

   User-added image

   Now you've successfully defined a SOAP endpoint that Privilege Manager knows how to call to initiate a ServiceNow request for approval.

   Next, navigate to the Thycotic Management Server Silverlight Console (installed in step 3):

1. Open an Internet Explorer Browser (not Edge) Go to https://DomainName/TMS/Setup and click on Security Manager Console. If this is your first time opening Silverlight, you may need to follow the download prompt to install.

In Thycotic's Silverlight Console you will first create a new ServiceNow Approval Process.

1. Click the Tasks tab, scroll to find Workflow in the left window and expand the window. Navigate to Automation | Approvals, right click on Approval Processes, then New | Approval Process | ServiceNow Approval Process

   ​User-added image

1. Your ServiceNow Approval Process will now appear under Approval Processes. Click on this.​
1. Next click the search icon and select the name of your ServiceNow Server that you created in step 6.
​
   User-added image

1. Click on Request Item and search for Thycotic | Execute Application Workflow , select this. It may take a few minutes to load.
1. Next to Create request service, type CreateExecuteAppApprovalRequest
   Next to Get request status service, type GetExecuteAppApprovalRequestStatus
   Next to Cancel request service, type CancelExecuteAppApprovalRequest

   > **Note**: The names of these services must be the same in Privilege Manager and ServiceNow or the integration will break. Click Save.

1. Now, still under Workflow in your Silverlight Tasks tab,
   1. Navigate to Automation | Approvals, right click on Approval Types and then New | Execute Application Approval Request
   1. Click Service Now Execute Application Process under Approval Types
   1. Select the ServiceNow Approval Process as your Process Handler. Click Save.

   User-added image

Lastly, you will need to create an action and attach it to a policy to manage what events you want sent to ServiceNow for approvals. To do this, navigate back to Privilege Manager (https://DomainName/TMS/PrivilegeManager):

User-added image

1. In the Privilege Manager Dashboard, go to Admin | Actions. Search for Approval Request Form Action, click this, then Create a Copy.

   ​User-added image

1. Name your new Action (ServiceNow Approval Request Form Action).
1. Click Edit. Next to Approval Type, search for ServiceNow Execute Application Request Type.

   You can also customize your Window Design and the Information Section to specify "This application has not been approved for use according to corporate policy. Please discontinue use or enter your justification to continue through ServiceNow," if desired. Click Save.

1. Next, navigate to Policies | Create New or find an existing policy that you want to use for ServiceNow Approvals.
   If you need help creating a new policy, see the Privilege Manager User Guide here.
1. On the Policy's detail view under the Actions tab, click Edit and Add Action. Search for the action you just created (ServiceNow Approval Request Form Action). Click Add, then Save.    
​
   User-added image

1. Update your endpoints by sending this new policy to target agents. Policies automatically update according to a schedule. For steps on how to do this immediately, see page 12 of the Privilege Manager User Guide here.

## Integration Workflow

Now that you have a policy attached to your ServiceNow integrated Action, the requests from your policy will be sent through ServiceNow for approval.

1. On your endpoint, perform the action that your policy targets for ServiceNow Approval. You will be prompted with a justification window to explain your request. To approve these requests, open your ServiceNow Dashboard.

​   User-added image

1. Go to MyApprovals in ServiceNow and you will see your new requests. Click Requested for details.
1. In the Request page you will be able to view details of what action is being requested, and you can Accept the action.
​
   User-added image

1. On your endpoint, the pending justification window will update to an Approved status, and the user will be able to access their requested application.

   ​User-added image