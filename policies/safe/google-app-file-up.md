[title]: # (Google App with File Upload)
[tags]: # (whitelist)
[priority]: # (4601)
# Google App with File Upload

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
