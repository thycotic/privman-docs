[title]: # (Cylance)
[tags]: # (integration)
[priority]: # (4)
# Set-up Cylance Integration

Cylance is an Artificial Intelligence Based Advanced Threat Prevention Solution for enterprise environments. Privilege Manager (v10.5+) integrates with Cylance to help you proactively act on any unknown applications that run in your environment to prevent potential malware attacks. The steps below walk through how to setup a Cylance Integration in Privilege Manager and then create an example policy to begin using Cylance intelligence in action across your environment.

Keep in mind that while the Cylance integration provides insight into threat analysis, ultimately you can use Privilege Manager policies to act or react in whatever way makes most sense to your organization.

## Cylance Connector Installation Steps (On-prem only)

1. Open a browser on your Privilege Manager Web Server, browse to https://[YourInstanceName]/TMS/Setup/
1. On the Currently Installed Products screen, choose Install/Upgrade Products.
1. Select option Thycotic Cylance Reputation Connector.
1. Click on __Install__ and Accept the End User License Agreement. You will see your Installation Progress. Click on “Show install Logs” link to check for any errors

   > **Note**: If the installation of Cylance initially fails, redirect to https://[YourInstanceName]/TMS/Setup/ and click the Repair button next to the Cylance Product.

1. Once the Installation is successful, click on the __Home__ button.

## Configuring the Cylance Connector

1. Navigate to __ADMIN | Configuration__ and select the __Reputation__ tab.
1. From the Select Rating Provider drop-down, select __Cylance Rating Provider__.

   ![Cylance set-up](images/cylance/cylance-1.png "Cylance Selection")
1. Click __Edit__.
1. Enter the required __Credentials__ and __Settings__ details. These details can be found in your Cylance account (login at protect.cylance.com).
   1. In our Cylance account, navigate to __Settings__ and select __Integrations__. You find the __Tenant Id__ on the right side of the Custom Applications area.
      ![protect.cylance.com](images/cylance/cylance-2-tenant.png "Cylance Settings overview")
   1. Select your Privilege Manager integration from the Custom Application list. You find the required __Application ID__  and __Application Secret__ on the left side of the page.
      ![Custom App](images/cylance/cylance-2.png "Cylance Custom Application")
1. Once the Cylance details are entered in Privilege Manger, click __Save__.

## Create a Cylance Security Rating Filter

1. Navigate to __ADMIN | More__ and select __Filters__.
1. Click __Add Filter__.
1. From the __Platform__ drop-down select either Windows or macOS.
1. From the __Filter Type__ drop-down select __Security Rating Filter__.
1. Name the policy and add a Description.
1. Next to __Security Rating System__, click __Application Control Rating System__.

   ![creating filter](images/cylance/cylance-3.png "Creating filter and selecting the Application Control Rating System")
1. Click the __+__ next to Cylance Rating System to add the system.

   ![add app control rating](images/cylance/cylance-4.png "Adding the Application Control Rating System")
1. Click __Create__.
1. Click __Edit__ to select the __Rating Level__ you wish to apply, the options are:

   * Unclassified
   * Allowlist
   * Greylist
   * Denylist

   You can also specify a Timeout value and Error Handling conditions on timeout and/or on failure, the options are:

   * Matched
   * Not Matched
1. Click __Save__.

## Create a Cylance Policy

After your Filter is created, 

1. Navigate to __ADMIN | Policies__ and click __Add New Policy__.
1. If you created a Windows filter, as we did in the example above, select Windows from the __Platform__ drop-down. 1. From the __Policy Type__ drop-down select a template that matches what you are trying to do, for example deny an application execution based on a bad security rating. Here we select Deny Application Execution.
1. Enter a name and description.
   ![policy](images/cylance/cylance-5.png "Creating a Policy")
1. Click __Create__.
1. Click __Edit__.
1. On the General tab, select the __Enabled__ checkbox. And adjust any other settings like the priority. Deny policies should have low priorities.
1. Select the __Conditions__ tab, then select __Add Application Target__.
1. Search for the Cylance filter created earlier. Select that filter and click __Add__.

   ![condition](images/cylance/cylance-6.png "Adding a target")
1. On the Actions tab, add an appropriate Action to be taken.

   ![action](images/cylance/cylance-6.png "Adding an action")
1. Click __Save__.
