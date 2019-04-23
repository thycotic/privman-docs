[title]: # (Set-up Cylance Integration)
[tags]: # (integration)
[priority]: # (5)
# Set-up Cylance Integration

Cylance is an Artificial Intelligence Based Advanced Threat Prevention Solution for enterprise environments. Privilege Manager (v10.5+) integrates with Cylance to help you proactively act on any unknown applications that run in your environment to prevent potential malware attacks. The steps below walk through how to setup a Cylance Integration in Privilege Manager and then create an example policy to begin using Cylance intelligence in action across your environment.

Keep in mind that while the Cylance integration provides insight into threat analysis, ultimately you can use Privilege Manager policies to act or react in whatever way makes most sense to your organization.

## Configuration Steps

1. Open a browser on your Privilege Manager Web Server, browse to https://[YourInstanceName]/TMS/Setup/
1. On the Currently Installed Products screen, choose Install/Upgrade Products.

​​   User-added image

1. Select option Thycotic Cylance Reputation Connector. Click on Install and Accept the End User License Agreement. You will see your Installation Progress. Click on “Show install Logs” link to check for any errors

   > **Note**: If the installation of Cylance initially fails, redirect to https://[YourInstanceName]/TMS/Setup/ and click the Repair button next to the Cylance Product.

1. Once Installation is successful, click on the Home button.
1. Navigate to Thycotic Privilege Manager | Admin | Configuration | Reputation tab.
1. Select Cylance Rating Provider from the Select Rating Provider drop down menu, then click Edit

​​User-added image

1. Enter the required Credentials and Settings Details. These details can be found in your Cylance account (login at protect.cylance.com) under Integrations | Custom Applications as shown below:

User-added image

1. When required details are entered, click Save.

​​User-added image

## Create a Cylance Security Rating Filter

1. Next, in Privilege Manager navigate to Admin | More | Filters, then click Add Filter.
1. Select a platform, then Security Rating Filter as a Filter Type. Name the policy and add a Description.
   ​​User-added image
1. Next to Security Rating System, Click Application Control Rating system, then select Cylance Rating System from available options, click __Create__.
​​​​​   User-added image
1. After the filter is created, click Edit and select the Rating Level type as per the requirement, then click Save.
​​   User-added image

## Create a Cylance Policy

1. After your Filter is created, Navigate to Admin | Policies | Add New Policy.
1. Select Windows as a Platform. Enter required details and click Create.

   User-added image

1. Click Edit and check the Enabled box. Select the Conditions tab, then select Add Application Target.
1. Search for the Cylance filter created in the previous steps. Select that filter and click Add.

User-added image

1. Next, select the Actions tab. Add an appropriate Action to be taken. Click the Save button to save the policy.

   User-added image