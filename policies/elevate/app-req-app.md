[title]: # (App Execution Requires Approval)
[tags]: # (elevate)
[priority]: # (3)
# App Execution Requires Approval

This policy type requires a user to provide a justification reason as to why they need to run a process (installer or executable).  Then, the reason is submitted to specified managers via Privilege Manager Tools | Manage Approvals for approval.  There are several pieces to the Actions in this policy. Because Conditions and Actions are independent, these actions for approval can be applied to any condition.  In this use case, we will apply this action to the LICEcap gif creator.  
First create a filter that will identify the process/executable on which Privilege Manager will act.

1. Like Step 1 in the previous example, Navigate to Dashboard | Filters, then click on Add Filter. In this use case, we will target the LICEcap application (LICEcap.exe).  Select Windows for your Platform, then Blank Win32 Executable Filter.  Add Name and Description. Click on Create. 
2. Click Edit at the bottom of the page. Enter LICEcap.exe in the File Name field under File Specifications as well as in the Original filename field under File Details. Click Save. 
Next create a workflow policy to assign to this filter: 
3. Navigate to Home | Policies, then click on Add New Policy. 
4. Select a platform, then Show All Templates. Select Other: Empty Policy. Name the policy Request Approval Policy, and add a description. Click Create.  
5. Edit, and check the Enabled box. 
6. Select the Conditions tab. Select Add Application Target. Search for the filter created in the previous steps (LICEcap).  Select that filter and click Add. 
7. Next, select the Actions tab. 
Select Add Action. In the search field, type Approval, and locate Approval Request Form Action.  Select this action and click on Add. 
8. Click on Save.  This saves the policy to the policy list accessed from the Home screen – click on Policies to view from the Home page.  Once the policy is delivered to the endpoint agent LICEcap.exe will require the user to enter a justification reason for running this application:  
Once the reason is entered by the user, the user clicks Continue to forward to the request to Privilege Manager for approval. On their desktop the Application Notice approval status is marked as Pending.
 Finally, a privilege manager user will approve this application request:
9. Return to the Privilege Manager Dashboard and navigate to TOOLS | Manage Approvals.  Click the + left of the request to view the options for approval.  Click on Approve, then select One Time or an allotted time frame for access, and click Approve. 
10. Now return to the desktop where the user initiated the executable, and you will see the request has been approved.  Click on Continue, and the user is allowed to run that executable. 
 
To adjust this policy to apply to specific users or endpoints, Click on the Advanced Policy View in the policy’s General tab, then click the Conditions tab to add Inclusion/Exclusion filters and Computer Groups.
