[title]: # (Set Up Secret Server Integration in Privilege Manager)
[tags]: # (Secret Server,integration,Privilege Manager)
[priority]: # (1000)
# Setting up Secret Server Integration in Privilege Manager

## Verify Web Services are Enabled in Secret Server

As a prerequisite, you need to make sure that your Secret Server instance has Web Services Enabled.

1. Navigate to __Admin | Configuration | Application Settings__.
1. Verify that under View Webservices the __Enable Webservices__ option is reflecting __Yes__.

## Setup Privilege Manager

1. Navigate to __Admin | Configuration__.
1. Click the __Foreign Systems__ tab.
1. Select __Secret Server__ from the list.
1. In the Name column click on __Default Secret Server__.
1. The Secret Server Foreign System page loads, click the __Edit__ button.
1. Under Settings, update the following:
   1. __Credential__: This is a Secret Server user (preferably an application account) that has at least the Administer Configuration and Administer Licenses permissions in Secret Server.
   1. __Secret Server Url__: This is the url that end users use to access Secret Server. __HTTPS__ is required. Also the validation on this field will reach out to Secret Server using the url provided. If it can’t be reached, or if the Secret Server version is lower than 10.6, there will be a 404 not found validation error.
   1. __TMS Url__: This is the url to access TMS itself. It is the url that end users use to access Privilege Manager, minus the /PrivilegeManager/ part at the end of the path.
1. Click the __Save__ button.

After these steps the Secret Server Foreign System is ready for use. If you need to enable or disable features for this integration, the Integration Feature list is below the Settings area on the page. Follow any of the links to turn features on and off. 

<!-- TODO: Name/describe list of features and why a user would want to enable/disable them. Add screen captures.>