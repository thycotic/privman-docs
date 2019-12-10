[title]: # (Priority)
[tags]: # (policy)
[priority]: # (6)
# Priority

In Privilege Manager your Policies are evaluated in a certain order for each application that runs. It is important to have an awareness of all policies that are defined and the order in which they are called by the agent. If one policy blocks an application and ends execution before a second policy that was intended to elevate privileges, then only the block will occur.

The Policy Priority setting can be found on the Policies main screen in the left column. By default, policies are ordered according to their priority. You can edit this setting under the General tab after clicking into a policy.

## Why Policy Priority Matters

To illustrate the way policies are applied in order, this use case will define two policies to 

* block MMC.EXE, but
* allow a specific MMC Snap-in.

### Deny MMC.EXE Policy setup

1. We will create a policy at a priority level of 50.  This policy will block the execution of MMC.EXE.

   Privilege Manager provides a filter to identify the executable mmc.exe. This can be used in this policy to block mmc.exe. Search for mmc.exe from the main screen search tool. Select the filter named Microsoft Management Console (mmc.exe). Review how the Filter is setup. Note that both File Name and File Path parameters are used.

2. Create the deny mmc.exe policy.

   1. From the home page, navigate to __ADMIN | Policies | Add New Policy__.
   1. Select Windows as a platform, Show All Templates, then Other: Empty Policy as the Template Type.
   1. Name the policy Deny Launching MMC Console Application Control Policy.
   1. Add a description.  
   1. Click __Create__.
   1. Enable the policy by clicking on the __Enabled__ check box.
   1. Set the __Policy Priority__ value to 50. (This level is not required, only defined for this use case.)
   1. Click on the __Conditions__ tab.
   1. Click on __+ Add Application Target__. Search for the MMC.EXE filter mentioned above.
   1. Click on __Add__.
   1. You can also set an exception filter to not have this policy apply to Administrators. Search for and select the filer named Administrators (Include Disabled). Click __Add__.
   1. Click on __Add Action__ under the Actions to apply to the application section.
   1. Search for the Application Denied Notification Action. Click __Add__.
   1. Click on __Save__. This saves the policy to the policy list accessed from the Home screen – click on Policies to view.  Once the policy is delivered to the endpoint agent, mmc.exe will be denied execution for all users without administrator credentials on all target computers. See details on how to deliver policies to the endpoint in the [Sending Policies to Endpoints](ac-policy-endpoints.md) section.

Once the policy is delivered to the endpoint, test running mmc.exe to see the results.
  
## Allow specific MMC Snap-in

Next, we will create a policy that has a priority of less than 50 and it will allow specific MMC snap-ins.  Having a priority less than 50 means this policy will be examined before the Deny MMC Console Application Control Policy.

1. As a short cut to this use case, start by making a copy of the policy we just created. Navigate to the General tab of the policy and click __Create a Copy__. Name the new policy Allow Print Management Plug-in Application Control Policy.
1. Click __Edit__ and select the __Enabled__ check box.
1. Set the __Policy Priority__ value to less than 50. (This level is not required, only defined for this use case.) This means that this policy will be examined prior to the policy that blocks the mmc console. If the conditions are met, printmanagement.msc will run with elevation.
1. Click on the __Conditions__ tab. Do not remove the Microsoft Management Console (mmc.exe) filter under Application Targets.
1. Privilege Manager provides a filter to identify the MMC snap-in for Print Management. This can be used in this policy to elevate printmanagement.msc.
   1. Select __Add Inclusion Filter__ and search for the printmanagement.msc Commandline Filter.
   1. Click __Add__, then __Save__. This filter will identify the mmc.exe file ONLY if the printmanagement.msc is run.
1. Click on the __Actions__ tab.
1. Click __Edit__ and delete the existing Application Denied Notification Action by clicking the trash can icon on the right side.
1. Click __Confirm Remove__.
1. Select __Add Action__ under the Actions to apply to the application section. Search for and add Add Administrative Rights action. 
1. Click __Save__. You will now see your two policies in your Policies List. Once this policy is delivered to the endpoint agent, printmanagement.msc will be elevated with administrative rights.

## Test this use case

1. Run MMC.EXE from an endpoint where the user is NOT an administrator. This MMC.EXE execution will be denied execution.
1. Run printmanagement.msc from an endpoint where the user is NOT an administrator. This MMC snap-in will run with elevation.
1. Change the Policy Priority of your “Allow Print Management Plug-in Application Control Policy” to Priority 51 rather than priority 49. Repeat the second test.

   when you now run printmanagement.msc, the application will be blocked despite your elevation policy. This is why it is crucial to keep the priority levels that are set for your policies in mind and adjust them to meet your intended system requirements.
