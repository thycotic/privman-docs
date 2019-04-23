[title]: # (Set-up Syslog Connection)
[tags]: # (integration)
[priority]: # (115)
# Set-up Syslog Connection

Privilege Manager can push out SysLog formatted messages on a set schedule. Note that this does not happen immediately upon events occurring. Listed below are steps for configuration and task creation for scheduling the action of sending Discovery Event logs to a SysLog server.

## Configuring Syslog Connection

To configure SysLog messages in Privilege Manager: 

1. Navigate to Admin | Configuration | Foreign Systems tab, then click on SysLog and Add New. Set a Name and the SysLog Server Address (either tcp or udp).

   **If you do not see "Syslog" listed under Admin | Configuration | Foreign Systems tab, navigate to https://[YourOrganizationURL]/TMS/Setup/ProductOptions/SelectProducts and check the Thycotic Syslog Connector option, then Install, Accept the License Terms and Conditions.

   User-added image

1. After adding a new Syslog connection, to manually send logs to your Syslog Server go to Admin | More… | Tasks. Expand the Server Tasks folder, then Foreign Systems, select SysLog and click Add New.

1. Select Send SysLog Application Events from the dropdown list, add a Name for this task and an Event Name (ex: “Privilege Manager Application Events”), the Event Severity, and then click Select Resource to select your SysLog server from above.

1. You can set the Security Rating Provider if you have VirusTotal configured, or skip.

1. Click Create.

Once created, you’ll be taken to the new Scheduled Task's page where you can specify how often you want events received by Privilege Manager (i.e. all events viewed in Admin | Event Discovery) to be pushed out to the SysLog server. The schedule can be hourly, every 30 minutes, daily, or whatever time period is preferred.

After this task runs and successfully completes, verify that Event Discovery events appear in your SysLog system.