[title]: # (Priority)
[tags]: # (policies)
[priority]: # (4104)
# Priority

In Privilege Manager your Policies are evaluated in a certain order for each application that runs. It is important to have an awareness of all policies that are defined and the order in which they are called by the agent. If one policy blocks an application and ends execution before a second policy that was intended to elevate privileges, then only the block will occur.

The Policy Priority setting can be found on the Policies main screen in the left column. By default, policies are ordered according to their priority. You can edit this setting under the General tab after clicking into a policy.
 
## Why Policy Priority Matters
To illustrate the way policies are applied in order, this use case will define two policies to 1) block MMC.EXE, but 2) allow a specific MMC Snap-in. 
Deny MMC.EXE Policy setup
First, we will create a policy at a priority level of 50.  This policy will block the execution of MMC.EXE. 
1.	Privilege Manager provides a filter to identify the executable mmc.exe.  This can be used in this policy to block mmc.exe. 
Search for mmc.exe from the main screen search tool.  Select the filter named Microsoft Management Console (mmc.exe) 
  
Review how the Filter is setup.  Note that both File Name and File Path parameters are used. 
Next, create the deny mmc.exe policy. 
2.	From the home page, navigate to ADMIN | Policies | Add New Policy, Select Windows as a platform, Show All Templates, then Other: Empty Policy as the Template Type.
Name the policy Deny Launching MMC Console Application Control Policy.  Add a description.  Click Create. 
Enable the policy by clicking on the Enabled check box. 
Set the Policy Priority value to 50. (This level is not required, only defined for this use case.) 
  
3.	Click on the Conditions tab. 
Click on + Add Application Target. Search for the MMC.EXE filter mentioned above.  Click on Add. 
  
4.	You can also set an exception filter to not have this policy apply to Administrators.  Search for and select the filer named Administrators (Include Disabled). Click Add.
  
5.	Click on Add Action under the Actions to apply to the application section. Search for the Application Denied Notification Action. Click Add. 
6.	Click on Save.  This saves the policy to the policy list accessed from the Home screen – click on Policies to view.  Once the policy is delivered to the endpoint agent, mmc.exe will be denied execution for all users without administrator credentials on all target computers.  
See details on how to deliver policies to the endpoint in the Sending Policies to Endpoints section. 
7.	Once the policy is delivered to the endpoint, test running mmc.exe to see the results.   
  
Allow specific MMC Snap-in 
Next, we will create a policy that has a priority of less than 50 and it will allow specific MMC snap-ins.  Having a priority less than 50 means this policy will be examined before the Deny MMC Console Application Control Policy. 
8.	As a short cut to this use case, start by making a copy of the policy we just created.  Accomplish this on the General tab of the policy by clicking Create a Copy. Name the new policy Allow Print Management Plug-in Application Control Policy. 
9.	Enable the policy by clicking Edit, then the Enabled check box. 
Set the Policy Priority value to less than 50. (This level is not required, only defined for this use case.) 
 
This means that this policy will be examined prior to the policy that blocks the mmc console.  If the conditions are met, printmanagement.msc will run with elevation. 
10.	Click on the Conditions tab. Do not remove the Microsoft Management Console (mmc.exe) filter under Application Targets. 
11.	Privilege Manager provides a filter to identify the MMC snap-in for Print Management.  This can be used in this policy to elevate printmanagement.msc. Select Add Inclusion Filter and search for the printmanagement.msc Commandline Filter.  Click Add, then Save.
This filter will identify the mmc.exe file ONLY if the printmanagement.msc is run. 
  
12.	Click on the Actions tab. Edit. Then delete the existing Application Denied Notification Action by clicking the trash can icon on the right side. Click Confirm Remove.
13.	Select Add Action under the Actions to apply to the application section. Search for and add Add Administrative Rights action. Click Save. You will now see your two policies in your Policies List:
 
Once this policy is delivered to the endpoint agent, printmanagement.msc will be elevated with administrative rights.   
14.	To test this use case:
a.	Run MMC.EXE from an endpoint where the user is not an administrator.  This MMC.EXE execution will be denied execution. 
b.	Next, run printmanagement.msc from an endpoint where the user is not an administrator.  This MMC snap-in will run with elevation. 
However, if you change the Policy Priority of your “Allow Print Management Plug-in Application Control Policy” to be set at Priority 51 rather than priority 49, when you return to your endpoint and run printmanagement.msc, the application will be blocked despite your elevation policy. This is why it is crucial to keep the priority levels that are set for your policies in mind and adjust them to meet your intended system requirements.
