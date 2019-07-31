[title]: # (Whitelisting)
[tags]: # (elevate)
[priority]: # (4210)
# Whitelisting Policies

Whitelisting is a type of policy that allows applications to run on your endpoints. You can think of Whitelisting as a neutral policy type because it does not alter an application’s default permissions, it merely signifies that the application is “known/trusted” and allowed to run. Although simple whitelisting follows normal, user-level credentials, whitelisted applications are also often paired with Elevation Policies outlined later in this guide. 
Example: Whitelist the Microsoft Security Catalog
This policy uses a built-in filter to whitelist Microsoft’s Signed Security Catalog. This filter is often used to dynamically whitelist update items from Microsoft.  Whitelisting these executables clears them so they are not effected by any other policy, (i.e. they are allowed to run). 
1.	Navigate to Admin | Policies, then click on Create a New Policy. 
2.	Select Windows as a Platform, Show All Templates as a Policy Type, and Other: Empty Policy as a Template Type. 
3.	Name the policy and add a Description. 
 
4.	Click Create
5.	Under the Conditions tab choose Edit, then Add Inclusion Filter. Type “Present in Signed Security Catalog” in the search bar to pull up the correct filter for this use case. Click Add, then Save
 
6.	Navigate to the General tab, Edit, and check the Enabled box to activate this policy. Click Save.
No action is required to add under the Actions tab, meaning that these items will be Whitelisted – i.e. they will be allowed to run with default permissions. 
Example: Whitelist Google Applications with File Upload
In evaluation and production installations, proactive introduction of executables into Privilege Manager can be accomplished with a feature called File Upload.  File Upload allows you to quickly introduce a file, then create a Filter and/or a Policy to govern the application. As example, here’s how to introduce the Chrome Installer into Privilege Manager and use the file information to whitelist other Google applications.
For this use-case you will need to have access to downloaded Chrome installer files.
1.	From the Privilege Manager home screen, navigate to TOOLS | File Upload. 
 
Click on Browse, and select a file to upload. Click Upload File
2.	When the file successfully uploads, choose Go to File Details.
 
3.	Click Add to Policy
 
4.	In the Add New Policy section that appears, select Other: Empty Policy as Policy Type, give it a Name and Description, and check the Company Name and File Must be Signed By Filters. Then click Create.
 
5.	This will bring you to your new policy’s detail view. Because this is a Whitelisting example, no extra Actions need to be assigned.  Under the General tab, select Edit, check Enabled, then click Save to activate.
