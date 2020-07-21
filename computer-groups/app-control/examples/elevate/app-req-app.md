[title]: # (Execution Requires Approval)
[tags]: # (elevate)
[priority]: # (10)
# Application Execution Requires Approval

This policy type requires a user to provide a justification reason as to why they need to run a process (installer or executable). Then, the reason is submitted to specified managers via Privilege Manager __Tools | Manage Approvals__ for approval. It also depends on whether or not the Manual Approval process is used. For instance, if you have configured Service Now as your approval process handler, these approval requests won't appear in the __Tools | Manage Approvals__ area. There are several pieces to the Actions in this policy. Because Conditions and Actions are independent, these actions for approval can be applied to any condition.  In this use case, we will apply this action to the LICEcap gif creator.  
First create a filter that will identify the process/executable on which Privilege Manager will act.

1. Navigate to __ADMIN | Filters__.

   ![ADMIN](images\app-req\ap-1.png)
   ![Filters](images\app-req\ap-2.png)
1. Click on __Add Filter__.
   >**Note:** In this use case, we will target the LICEcap application (LICEcap.exe).

1. From the Platform drop-down select __Windows__.
1. From the Filter Type drop-down select __Blank Win32 Executable Filter__.  
1. Add a name and description, click __Create__.

   ![New filter](images\app-req\ap-3.png)
1. Click __Edit__ at the bottom of the page.
1. Enter __LICEcap.exe__ in the File Name field under File Specifications as well as in the Original filename field under File Details.

   ![Filter options](images\app-req\ap-4.png)
1. Click __Save__.

## Create a workflow policy to assign to this filter

1. Navigate to __ADMIN | Policies__.
1. Click on __Add New Policy__.

   ![New policy](images\app-req\ap-5.png)
1. From the Platform drop-down select __Windows__.
1. From the Policy type drop-down select __Show All Templates__.  
1. From the Template Type drop-down select __Other: Empty Policy__.
1. Add a name and description, click __Create__.

   ![Create new policy](images\app-req\ap-6.png)
1. Click __Edit__ and check the __Enabled__ box.

   ![Enable policy](images\app-req\ap-7.png)
1. Navigate to the __Conditions__ tab.
1. Click Add __Application Target__.
1. Search and select the __(LICEcap)__ filter.  
1. Click __Add__.

   ![Add application target](images\app-req\ap-8.png)
1. Navigate to the __Actions__ tab.
1. Click on __add Action__.

   ![Add action](images\app-req\ap-9.png)
1. In the search field, type __Approval__.
1. Select __Approval Request Form Action__.
1. __Add__ the action.
1. Click on __Save__.  

   ![Approval Request Form Action](images\app-req\ap-10.png)
1. This saves the policy to the policy list accessed from the Home screen
1. Click on Policies to view from the Home page.  

   * Once the policy is delivered to the endpoint agent LICEcap.exe will require the user to enter a justification reason for running this application:  
   * Once the reason is entered by the user, the user clicks Continue to forward to the request to Privilege Manager for approval. On their desktop the Application Notice approval status is marked as Pending.
   * Finally, a privilege manager user will approve this application request

## To Approve Requests

1. Return to the Privilege Manager Dashboard and navigate to __TOOLS | Manage Approvals__.  

   ![Manage Approvals](images\app-req\ap-11.png)
1. Click the __+__ left of the request to view the options for approval.  
1. Click on __Approve__.
1. Select __One Time or an allotted time frame for access__ and __Manage Approve__.
1. You can now return to the desktop where the user initiated the executable, and you will see the request has been approved.
1. Click on __Continue__ and the user is allowed to run that executable.

   >**Note:** To adjust this policy to apply to specific users or endpoints, Click on the Advanced Policy View in the policy’s General tab, then click the Conditions tab to add Inclusion/Exclusion filters and Computer Groups.
