[title]: # (Whitelisting)
[tags]: # (elevate)
[priority]: # (4210)
# Whitelisting Policies

Whitelisting is a type of policy that allows applications to run on your endpoints. You can think of Whitelisting as a neutral policy type because it does not alter an application’s default permissions, it merely signifies that the application is “known/trusted” and allowed to run. Although simple whitelisting follows normal, user-level credentials, whitelisted applications are also often paired with Elevation Policies outlined later in this guide. 
<!-- TODO insert link for later in this guide -->

## Example: Whitelist the Microsoft Security Catalog

This policy uses a built-in filter to whitelist Microsoft’s Signed Security Catalog. This filter is often used to dynamically whitelist update items from Microsoft.  Whitelisting these executables clears them so they are not effected by any other policy, (i.e. they are allowed to run).

1. Navigate to __Admin | Policies__, then click on Create a New Policy.
1. From the Platform drop-down select __Windows__.
1. Select __Show All Templates as a Policy Type__ click __Other: Empty Policy as a Template Type__.
1. Name the policy and add a Description.
1. Click __Create__.
1. Under the Conditions tab choose __Edit__, then __Add Inclusion Filter__.
1. Type __Present in Signed Security Catalog__ in the search bar to pull up the correct filter for this use case.
1. Click __Add__.
1. Click __Save__.
1. Navigate to the __General__ tab and click __Edit__.
1. Check the __Enabled__ box to activate this policy.
1. Click __Save__.

There is no need to add actions under the Actions tab, because these applications are Whitelisted, they are allowed to run with default permissions.

## Example: Whitelist Google Applications with File Upload

In evaluation and production installations, proactive introduction of executables into Privilege Manager can be accomplished with a feature called File Upload.  File Upload allows you to quickly introduce a file, then create a Filter and/or a Policy to govern the application. As example, here’s how to introduce the Chrome Installer into Privilege Manager and use the file information to whitelist other Google applications.

For this use-case you will need to have access to downloaded Chrome installer files.

1. From the Privilege Manager home screen, navigate to __TOOLS | File Upload__.
1. Click __Browse__ and select a file to upload.
1. Click __Upload File__.
1. When the file successfully uploads, click __Go to File Details__.
1. Click __Add to Policy_._
1. In the __Add New Policy__ section select __Other: Empty Policy as Policy Type__.
1. Enter a Name, Description.
1. Verify the __Company Name__ and __File Must be Signed By Filters__.
1. Click __Create__. This will bring you to your new policy’s detail view. Because this is a Whitelisting example, no extra Actions need to be assigned.  
1. Navigate to the General tab and select __Edit__.
1. Select __Enabled__ to enable the policy.
1. Click __Save__.
