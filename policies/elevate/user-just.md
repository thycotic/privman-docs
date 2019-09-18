[title]: # (User Justification Required to Run)
[tags]: # (elevate)
[priority]: # (4)
# User Justification Required to Run

This policy type requires a user to provide a justification for why they need to run an application before elevating with administrator privileges.  User Justification refers to the policy action.  Since Conditions and Actions are independent, this action can be applied to any condition.  In this use case, we will simply apply this action to a specific application.

First, create a filter that identifies the application.

1.	Navigate to Dashboard | Filters, then click on Add Filter. In this use case, we will target the Calculator application (calc.exe).  Select Windows for your Platform, then Blank Win32 Executable Filter.  Add Name and Description. Click on Create. 
2.	Click Edit at the bottom of the page. Enter calc.exe in the File Name field. Click Save. 
This created a Condition filter we can now use in the policy to govern the calc.exe executable. Next we’ll create the policy that requires justification. 
3.	Navigate to Home | Policies, then click on Add New Policy. 
4.	Select Windows as a Platform, then Show All Templates. From the Template Type dropdown select Elevate: Add Administrator Rights to Specific Applications with Justification. Add a Name and Description. Click Create.
5.	Edit and check the Enabled box and click the Advanced Policy View button (if in the Simple Policy View).
6.	Select the Conditions tab. Select Add Application Target and search for the name of your Calculator filter. Select this filter and Click Add.  
7.	Click on Save.  This saves the policy to the policy list accessed from the Home screen – click on Policies to view from the Home page.  Once the policy is delivered to the endpoint agent, calc.exe will require the user to enter a justification reason for running this application.  This policy will be applied to all users on all computers.  See details on how to deliver policies to the endpoint in a later section. 
To adjust this policy to apply to specific users or endpoints, Click on the Advanced Policy View in the policy’s General tab, then click the Conditions tab to add Inclusion/Exclusion filters and Computer Groups.
8.	The justification message the user will see as a result of this policy: 
  
When the user adds a reason and clicks the Continue button, the application is allowed to execute. You can then view a user’s provided reasons in Privilege Manager on the Events Discovery | Policy Activity page or under Reports | Application Justification Summary Details Report. 
