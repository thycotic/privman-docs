[title]: # (Process Explorer)
[tags]: # (troubleshooting)
[priority]: # (3)
# Using Process Explorer for Troubleshooting a Policy

This topic describes how to troubleshoot a policy with Process Explorer. Process Explorer is used to look at policies that grant administrative privileges, but don't seem to work when

* an application is accessed, or
* actions are supposed to run.

In the example below the policy allows resource monitor to run but the application is blank due to not having sufficient Windows Privileges. You can use Process Explorer to determine the correct Windows Privileges to add to the policy in order to use the resource monitor application.

## Detailed Troubleshooting Steps

1. Download [Process Explorer from the Mircosoft website](https://docs.microsoft.com/en-us/sysinternals/downloads/process-explorer) and extract the downloaded ProcessExplorer.zip file locally on your system.
1. Open __Process Explorer__.
1. Next open __Resource Monitor__ as the Administrator. 
1. Navigate back to the Process Explorer Window and find the Resource Monitor application (perfmon.exe).

   ![step-1](images/process-ex/proc-ex-1.png "Locate Resource Monitor in the Process Explorer application")
1. Right-click and select __Properties__.
1. Select the __Security__ tab.
1. Under the Privilege section, you can see all the flags that are enabled in order to use the application.

   ![step-2](images/process-ex/proc-ex-2.png "Privilege list under properties")
1. Launch Privilege Manager and navigate to __Admin | Application Policies__.
1. Select the policy that elevates privileges to run __Resource Monitor__.
1. Under __Adjust Process Rights__, modify settings.

   ![process rights](images/process-ex/proc-ex-3.png "Elevate Resource Monitor policy adding actions")
   1. Select Add Administrative Rights or the elevation action you are using.
1. The new window will display what Windows Privileges the action is using.

   ![Privileges used by the policy](images/process-ex/proc-ex-4.png)
1. Under __Windows Privileges__, click __Edit__. (For this step you will have to determine which flags are enabled in Process Explorer in order to add the additional Windows Privileges to the action.)
1. In another window navigate to the following Microsoft web site @ https://docs.microsoft.com/en-us/windows/win32/secauthz/privilege-constants. The site will show the name of the Windows Privileges, along with the user right information that needs to be added to the action in Privilege Manager.

   For Example: The privileges listed under the properties security tab show __SeCreateGlobalPrivilege__ as enabled. On the Microsoft website for Privilege Constants @ https://docs.microsoft.com/en-us/windows/win32/secauthz/privilege-constants the user right for SeCreateGlobalPrivilege privilege is: __Create global Objects__.
1. Enter the User right into the search box and then select the user right from the returned list. In this example enter in Create global objects.

   ![search](images/process-ex/proc-ex-6.png "Search for and add Create Global Objects")
1. Click __Add__.
1. Remove any actions you don't need.
1. Click __Update__.
1. Click __Save Changes__.

Once the agent has received the updated policy, the additional Windows Privileges will be applied to the application next time it is launched.
