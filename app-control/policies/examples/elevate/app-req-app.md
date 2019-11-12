[title]: # (App Execution Requires Approval)
[tags]: # (elevate)
[priority]: # (10)
# App Execution Requires Approval

This policy type requires a user to provide a justification reason as to why they need to run a process (installer or executable). Then, the reason is submitted to specified managers via Privilege Manager __Tools__ | __Manage Approvals__ for approval. It also depends on whether or not the Manual Approval process is used. For instance, if you have configured Service Now as your approval process handler, these approval requests won't appear in the __Tools__ | __Manage Approvals__ area. There are several pieces to the Actions in this policy. Because Conditions and Actions are independent, these actions for approval can be applied to any condition.  In this use case, we will apply this action to the LICEcap gif creator.  
First create a filter that will identify the process/executable on which Privilege Manager will act.

1. Navigate to __ADMIN__ | __Filters__.

   ![ADMIN](images\app-req\ap-1.png)
   ![Filters](images\app-req\ap-2.png)
1. Click on __Add Filter__.
   >**Note:** In this use case, we will target the LICEcap application (LICEcap.exe).

1. Click __Windows__ for your Platform, then __Blank Win32 Executable__ Filter.  
1. Add __Name__ and __Description__. Click on __Create__.

   ![New filter](images\app-req\ap-3.png)
1. Click __Edit__ at the bottom of the page.
1. Enter __LICEcap.exe__ in the File Name field under File Specifications as well as in the Original filename field under File Details.

   ![filter options](images\app-req\ap-4.png)
1. Click __Save__.

## Create a workflow policy to assign to this filter

1. Navigate to __Home__ | __Policies__.
1. Click on __Add New Policy__.

   ![new policy](images\app-req\ap-5.png)
1. Click a __platform__ | __Show All Templates__.
1. Click on __Other: Empty Policy__.
1. Name the policy __Request Approval Policy__, | __add a description__.
1. Click __Create__.  

   ![create new policy](images\app-req\ap-6.png)
1. Click __Edit__ | check the __Enabled__ box.

   ![Enable policy](images\app-req\ap-7.png)
1. Click the __Conditions__ tab | Add __Application Target__.
1. Search for the filter created in the previous steps __(LICEcap)__.  
1. Click that filter | __Add__.

   ![add application target](images\app-req\ap-8.png)
1. Click the __Actions__ tab  | __add Action__.

   ![add action](images\app-req\ap-9.png)
1. In the search field, type __Approval__.
1. Locate __Approval Request Form Action__ | Click this action | __Add__.
1. Click on __Save__.  

   ![Approval Request Form Action](images\app-req\ap-10.png)
1. This saves the policy to the policy list accessed from the Home screen
1. Click on Policies to view from the Home page.  

   * Once the policy is delivered to the endpoint agent LICEcap.exe will require the user to enter a justification reason for running this application:  
   * Once the reason is entered by the user, the user clicks Continue to forward to the request to Privilege Manager for approval. On their desktop the Application Notice approval status is marked as Pending.
   * Finally, a privilege manager user will approve this application request

## To Approve Requests

1. Return to the Privilege Manager Dashboard and navigate to __TOOLS__ | __Manage Approvals__.  

   ![Manage Approvals](images\app-req\ap-11.png)
1. Click the __+__ left of the request to view the options for approval.  
1. Click on __Approve__ | click __One Time or an allotted time frame for access__ |__Approve__.
1. You can now return to the desktop where the user initiated the executable, and you will see the request has been approved.
1. Click on __Continue__ and the user is allowed to run that executable.

   >**Note:** To adjust this policy to apply to specific users or endpoints, Click on the Advanced Policy View in the policy’s General tab, then click the Conditions tab to add Inclusion/Exclusion filters and Computer Groups.
