[title]: # (SDDL by Client ID)
[tags]: # (intro)
[priority]: # (6020)
# Set Security For Service Control By Account

Setting up the __Set Security For Service Control By Account task__ allows Privilege Manager Administrators to restrict agent control rights on the endpoints. The tasks allows to pick one or more user/group accounts to be associated with the SDDL used to secure services on the endpoints.

The procedure below describes the required steps to run this task once on the targeted endpoints. This task is not suited for scheduling. Once the task runs on the targeted endpoints, it won't need to be applied again to the same set of resources.

## Creating the Task

To secure agent access control on the endpoints set up the __Set Security For Service Control By Account Task__ based on the following steps:

1. Navigate to __Admin | More__ and select the __Tasks__ link.
1. Open the Local Security folder.

   ![Local Security Folder](images/sddl-client.png)
1. Select __Set Security For Service Control By Account__ from the list of available Tasks.
1. Click __Run__.

   ![Local Security Folder](images/sddl-client-2.png)
1. Under Resources click the __Select resource...__ link to select the computers or groups to be targeted by the task.

   ![Local Security Folder](images/sddl-client-3.png)
   1. Depending on your Local Security set-up this table can contain many records. We recommend using the filter function on the name column to filter and then set the checkboxes for specific items. Multiple resources can be specified.

      ![Local Security Folder](images/sddl-client-4.png)

1. Under Services click the __Select resource...__ link to select the Services to be targeted by the task.
   1. In the Name filter enter acs and select the ArelliaACSvc from the list of filtered items, click the __+__ button.

      ![Local Security Folder](images\sddl-client-6.png)
1. Under User Accounts click the __+__ button and use the search field to find the specific user account that has permissions to make changes to the Agent services.
1. Click __Run Task__.

Once the task runs the Start and Stop options for the two agent services is disabled for all users that don't have the Agent Administrator role. Due to the agents pulling any new commands based on schedule or connectivity, the execution of the task at the endpoint might not be immediate.
