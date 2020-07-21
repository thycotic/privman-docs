[title]: # (Sending Policies to Endpoints)
[tags]: # (Application Control,Policy,Endpoints)
[priority]: # (4)
# Sending Policies to Endpoints

After setting up your first policies, keep in mind that even after you enable them, new policies are not immediately sent to target endpoints. Instead, policies are updated on endpoints via the schedule defined by the Update Applicable Policies task. By default this tasks runs once daily.

1. Search for the _Update Applicable Policies_ task:

   ![remote client task](images/tasks/update-applicable-policies.png "Search results returned")
1. Select the __Update Applicable Policies (Windows)__ for example.
1. To edit the time scheduled that sets off this task, under Job schedule click __Add Trigger__.

   ![add trigger](images/tasks/trigger.png "Add Trigger option on task page")
   1. Select to run this schedule __Once__ on demand and make sure the time indicated is in the future. Clicking __Show Advanced__ give you more options for the modification.

   ![modify](images/tasks/trigger-edit.png "Modify the schedule")

   In production environments having a delayed deployment schedule prevents performance issues when adjusting policies and rolling them out across a large number of agents on your network. However, when setting up new policies you may want to immediately activate them on testing endpoints and verify your configurations are working correctly.
1. Click __Save__. The data under __Job Schedule__ indicates to run once.

   ![new schedule](images/tasks/schedule.png "Job Schedule indicated to run once")
1. Click __Save Changes__ for the modification to take effect.

## View Deployment Status

Within a Policy’s Detail View, verify the deployment status. This will tell you how many computers the policy is already deployed on:

![Deployment Status](images/tasks/deployment.png "Deployment Status")

>**Note**: If the deployment status number is 0 or incorrect, it is possible that the _Resource and Collection Targeting Update_ task needs to run.

## Update Policies on an Endpoint using Powershell (prior version 10.7)

On Privilege Manager version prior to 10.7, the fastest way to deploy or update your policies on a specific testing endpoint is by running a simple Powershell script directly on your test machine where a Thycotic Agent is installed.

1. On your endpoint machine, right-click on the Windows Powershell application and select Run as Administrator.
1. Navigate to the Agent directory by entering the following command and then enter:

   ```shell
   cd "C:\Program Files\Thycotic\Powershell\Arellia.Agent"
   ```
1. Next type

   ```shell
   UpdateClientItems.ps1
   ```
1. Hit enter.

>**Note**:
>If your policies are not immediately updated, wait a few minutes and try running the script again.

After you’ve updated your test endpoints, you can try running applications that are targeted by your policies to make sure the policies are configured correctly. You will also see the policy's Deployment status information updated if refreshed.

## Agent Event Log Viewer

Another helpful place to look when setting up new policies is your Agent’s Event Log Viewer. On your endpoint machine,

1. Navigate to your Thycotic Agent files. This is usually located in `C:\Program Files\Thycotic\Powershell\Arellia.Agent`.
1. Right-click on __AgentLogViewer__ and select the Log Viewer button. This opens your Agent Event Log Viewer, which shows updates in real time as the agent communicates with the Privilege Manager server. For remote access, Agent logs are also viewable through the Windows Event Viewer.
1. Scroll all the way to the top of the page to see the most recent activity from your Thycotic Agent.
1. Deselect the Information box on the upper right-hand corner to narrow search results for any Errors and Warning messages that may be occurring. You can also double-click any line item for more detailed information about each event.

Now that you know how to update your endpoints and check to make sure your policies are working, it’s time to start building new policies!
