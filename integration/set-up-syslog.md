[title]: # (Set-up SysLog Connection)
[tags]: # (integration)
[priority]: # (115)
# Set-up Syslog Connection

Privilege Manager can push out SysLog formatted messages on a set schedule. Note that this does not happen immediately upon events occurring. Listed below are steps for configuration and task creation for scheduling the action of sending Discovery Event logs to a SysLog server.

## Configuring Syslog Connection

To configure SysLog messages in Privilege Manager:

1. Navigate to __Admin | Configuration__ and select the Foreign Systems tab.
1. Click on SysLog and __Add New__. Set a Name and the SysLog Server Address (either tcp or udp). The default is udp on port 514.

   ![New Syslog Server Page](images/syslog/fs_new_syslog.png)

1. Once the server is created, you can use __Edit__ to change any of the configuration settings.

   ![Edit Syslog Server](images/syslog/edit_syslog_server.png)

   The protocol drop-down options are UDP, TCP, and HTTPS. HTTPS supports integrations with DEVO.

## Setting up Syslog Server Tasks

1. After adding a new Syslog connection, to manually send logs to your Syslog Server go to __Admin | More…__ and select __Tasks__.
1. Expand the Server Tasks folder, then Foreign Systems, select SysLog and click __Add New__.
1. From the Template drop-down, select __Send SysLog Application Events__.
1. Add a Name for this task, an Event Name (e.g. “Privilege Manager Application Events”), and Event Severity.
1. Click __Select resource__ to select your SysLog server foreign system (configured above).
1. Optionally also enter a Security Ratings Provider, depending on your other integrations.

   ![Create Task](images/syslog/create_syslog_task.png)

1. Click __Create__.

Once created, you’ll be taken to the new Scheduled Task's page where you can run the task on demand and/or specify how often you want events received by Privilege Manager (i.e. all events viewed in Admin | Event Discovery) to be pushed out to the SysLog server. The schedule can be hourly, every 30 minutes, daily, or whatever time period is preferred.

After this task runs and successfully completes, verify that Event Discovery events appear in your SysLog system.

## Troubleshooting if Syslog Option is Missing under Foreign Systems

If you are a Privilege Manager Cloud customer, contact Thycotic support to have it added to your instance.

On-premises customers, navigate to https://[YourOrganizationURL]/TMS/Setup/ProductOptions/SelectProducts and check the Thycotic Syslog Connector option. Install the Syslog Connector and accept the License Terms and Conditions.