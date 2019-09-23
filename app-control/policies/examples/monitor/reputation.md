[title]: # (Reputation Checking)
[tags]: # (greylist)
[priority]: # (4502)
# Reputation Checking

<!-- TODO: Screen captures and cleaning up the procedural steps -->

Privilege Manager analyzes applications in real-time.  This unique feature allows for reputation analysis of any unknown applications that will mitigate endpoint attacks from Ransomware, Zero-day attacks, Drive-by Downloads, and other unknown malicious software.

The greylist approach used here is that all applications that meet a general condition (i.e. executed from a specific directory or directories) will be sent to VirusTotal for a reputation check. For this use case we will perform real-time reputation analysis of unknown applications using VirusTotal.

For information and setup steps to configure Reputation using Cylance, see our Cylance Integration Guide instead.

First, you will need to integrate Privilege Manager and VirusTotal by following the Integration steps listed in the Setting Up VirusTotal for Reputation Checking section of this User Guide. That section will walk you how to do the following:

1. Configure VirusTotal Ratings Provider
2. Install VirusTotal in Privilege Manager
3. Create a Security Rating Filter for VirusTotal

Once the above steps are complete, follow these steps to create a Reputation Checking Policy:
1. After your Security Rating Filter for VirusTotal is created, Navigate to Home | Policies, then click on Add New Policy. 
2. Select Windows as a Platform, Show All Policies as a Policy Type, then Other: Empty Policy. 
Name the policy Deny Applications – VirusTotal Rating, and add a description Prevents applications flagged by VirusTotal as bad. Click Create. 
3. Click Edit and check the Enabled box. Select the Conditions tab. Select Add Application Target.
Search for the filter created in the previous steps (VirusTotal).  Select that filter and click Add. 
4. Next, select the Actions tab. Select Add Action. In the search field, type Application Denied, and locate Application Denied Message Action.  Select this action and click on Add. 
This VirusTotal policy requires an additional step of creating a filter to be added as an Inclusion Filter under the Conditions tab.  In this use case, we only want to send applications to VirusTotal for a reputation check that are in the user’s Downloads and Temp directories. 
Open another browser tab and open another Privilege Manager session so you can return to this policy in step 8 below. 
5. Start by searching for this policy in the Search Items filed at the top of the console page: User’s Temp Directory File Specification Filter. 
6. Select the filter Users’ Temp Directory File Specifications Filter.  Click Create a Copy at the bottom of the page.  Name the new filter User’s Downloads Directory File Specification Filter. 
Click Create. 
7. Click on Edit, and change the regular expression in the Path filed to the following: (c:\\users\\[^\\]+\\downloads). Save your changes.

Finally, combine the 2 filters into a single filter to target both directories:

1. Click Create a Copy at the bottom of this filter’s page, and name the new filter User’s Directory Collection File Specification Filter. Click Create.
1. Edit, then Clear the entry in the Path field.
1. Click the Add button to the right of the Include only filters near the bottom of the page under 
Additional Filters (optional).  Type User’s to search for the filters identified and created in the previous steps:

* User’s Downloads Directory File Specification Filter 
* User’s Temp Directory File Specification Filter 
Click on Save. 
1. Now, add this new filter to the Deny Applications – VirusTotal Rating policy by clicking on the Add Inclusion Filter under the Conditions tab. 
1. Search for and add the filter just created named User’s Directory Collection File Specification Filter. Click on Add. Save changes.

To adjust this policy to apply to specific users or endpoints, click on the Advanced Policy View in the policy’s General tab, then click the Conditions tab to add Inclusion/Exclusion filters and Computer Groups.

>**NOTE**:
>This policy will send any application run from the user’s Downloads or Temp directory to VirusTotal for a reputation check in real-time.  If the application is graded with Bad from VirusTotal, the application will be denied.

To view a File Security Ratings report, from the main page go to REPORTS | File Security Rating Details Report. To see details of the applications in the report, click on the file name in the File column. 
