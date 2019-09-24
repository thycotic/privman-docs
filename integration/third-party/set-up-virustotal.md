[title]: # (Set-up VirusTotal)
[tags]: # (integration)
[priority]: # (9105)
# Set-up VirusTotal Connection

Privilege Manager can perform real-time reputation checks for any unknown applications by integrating with analysis tools like VirusTotal. This article shows how to set up the integration between Privilege Manager and VirusTotal and then create a greylisting policy in Privilege Manager for reputation checking.

## VirusTotal API Key

As a first step the VirusTotal Ratings Provider has to be configured. For this,

1. Sign up for a Free VirusTotal account at https://www.virustotal.com/.
1. Sign in to VirusTotal and find your API key under your __Username | Settings | API Key__.  

## Install VirusTotal

As a second step VirusTotal needs to be installed in Privilege Manager. 

> **Note**: You need outbound access on your server for that installation.

1. Open a browser on your Privilege Manager Web Server.
1. Browse to https://YourInstanceName/TMS/Setup/.
1. On the Currently Installed Products screen, choose Install/Upgrade Products. <!-- screen capture-->
1. Check the Thycotic VirusTotal Reputation Connector, click __Install__. Then __Accept__ the End User License Agreement. You will see your Installation Progress. <!-- screen capture-->

   > **Note**: If the installation of VirusTotal initially fails, redirect to https://YourInstanceName/TMS/Setup/ and click the __Repair__ button next to the VirusTotal Product.

1. Navigate to __Thycotic Privilege Manager | Admin | Configuration | Reputation__ tab.
1. Select __VirusTotal Rating Provider__ from the Select Rating Provider drop down menu, then click __Edit__ and enter the required __Credentials__ and __Settings__ Details. <!-- screen capture-->
1. Click the __Home__ button. Navigate to __Admin | Configuration | User Credentials__. Click the __+ User Credential__ option, then __VirusTotal API Key__. <!-- screen capture-->
1. Next, create a Security Rating Filter for VirusTotal:
   1. Navigate to __Home | Filters__, the click __Add Filter__.
   1. Select a platform, then __Security Rating Filter__ as a Filter Type.  Name the policy and add a description.
   1. Next to Security Rating System, select __View Parameters__ and then __VirusTotal as a Resource__, click __Create__. <!-- screen capture-->
1. Create a Policy for VirusTotal:
   1. After your Filter is created, Navigate to __Home | Policies__, then click on __Add New Policy__.
   1. Select Windows as a Platform, __Show All Policies__ as a Policy Type, then __Other: Empty Policy__.
   1. Name the policy __Deny Applications – VirusTotal Rating__, and add a description _Prevents applications flagged by VirusTotal as bad_, click __Create__. <!-- screen capture-->
1. Next, select the Actions tab. Select Add Action. In the search field, type Application Denied, and locate Application Denied Message Action.  Select this action and click on Add.

   This VirusTotal policy requires an additional step of creating a filter to be added as an Inclusion Filter under the Conditions tab.  In this use case, we only want to send applications to VirusTotal for a reputation check that are in the user’s Downloads and Temp directories.

   Open another browser tab and open another Privilege Manager session so you can return to this policy in step 8 below.

1. Start by searching for this policy in the Search Items filed at the top of the console page: User’s Temp Directory File Specification Filter. <!-- screen capture-->
1. Select the filter Users’ Temp Directory File Specifications Filter, click __Create a Copy__ at the bottom of the page.  Name the new filter User’s Downloads Directory File Specification Filter, click __Create__.
1. Click on __Edit__, and change the regular expression in the Path filed to the following: (c:\\users\\[^\\]+\\downloads), save your changes. <!-- screen capture-->
1. Finally, combine the 2 filters into a single filter to target both directories:
   1. Click Create a Copy at the bottom of this filter’s page, and name the new filter User’s Directory Collection File Specification Filter. Click Create.
   1. Edit, then Clear the entry in the Path field.
   1. Click the __Add__ button to the right of the Include only filters near the bottom of the page under Additional Filters (optional). Type User’s to search for the filters identified and created in the previous steps:
      * User’s Downloads Directory File Specification Filter
      * User’s Temp Directory File Specification Filter
   1. Click on __Save__.
1. Now, add this new filter to the Deny Applications – VirusTotal Rating policy by clicking on the Add Inclusion Filter under the Conditions tab.
1. Search for and add the filter just created named User’s Directory Collection File Specification Filter. Click on Add. Save changes. <!-- screen capture-->
1. To adjust this policy to apply to specific users or endpoints, click on the Advanced Policy View in the policy’s General tab, then click the Conditions tab to add Inclusion/Exclusion filters and Resource Targets. <!-- screen capture-->

> **Note**: This policy will send any application run from the user’s Downloads or Temp directory to VirusTotal for a reputation check in real-time. If the application is graded with Bad from VirusTotal, the application will be denied.

To view a File Security Ratings report, from the main page go to REPORTS | File Security Rating Details Report. To see details of the applications in the report, click on the file name in the File column.