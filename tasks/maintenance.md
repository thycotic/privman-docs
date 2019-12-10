[title]: # (Maintenance)
[tags]: # (admin)
[priority]: # (6002)
# Maintenance

Privilege Manager has many tasks that can be run to ensure that the data in the database is up-to-date and to purge old or unwanted information. This section provides an overview of the maintenance tasks and other schedulable tasks in Privilege Manager.

Determining how often to schedule maintenance tasks depends on the associated items, like events, files, computers, etc. and their build up. These tasks have default __parameters__ assigned but are not scheduled to run. Privilege Manager administrators should schedule these tasks based on their needs and system performance.

The primary maintenance tasks that will need to be scheduled to ensure Privilege Manager databases do not grow too excessively are the

* Purge Maintenance - Application Control Events and
* Purge Maintenance - Files Undiscovered tasks and,
* in pre-10.5 systems, the
  * Purge Maintenance - Completed File Upload Sessions and
  * Purge Maintenance - Incomplete File Upload Sessions tasks.

## Maintenance Tasks

These maintenance tasks can be found at

* __ADMIN | Configuration | General (tab)__ or
* __ADMIN | Tasks | Jobs__ and
* __Tasks | Infrastructure Scheduled Activities | Maintenance Tasks__.

### Assign Orphaned Agent Uploads

This task will assign agent event uploads that have been orphaned.

__Parameters__: Max records [default setting = 2500]

<!-- with 10.7: by default ### Clear Client Item Cache

This server task will clear entries from the Client Item Cache that are older than the time period specified.

__Parameters__: Delete Message History older than [default setting = 30 day(s)]

__Notes__: This is mainly a diagnostics tool and should not need to be scheduled. -->

### Delete Old Performance Counter Events

This task will delete internal performance counter events last updated before the specified time.

__Parameters__: Can be set to Seconds, Minutes, Hours, Days, and Weeks. The default is 1 Day.

### Initialize Item Change History

This task is run after installs to ensure items with change tracking enabled have initial history entries.

### Purge Agent and Gauge Data for Deleted Computers

This task will delete orphaned data from AgentActivity, AgentRegistration, and GaugeInstanceState.

__Notes__: This can be helpful to run, to remove unwanted data for computers that have been deleted from Privilege Manager.

### Purge Duplicate Computers

Remove duplicate computers.

__Notes__: When AD sync occurs, Privilege Manager creates a new object in the database for each computer object. When the agent is installed, it references this same object. If the agent is installed before AD sync occurs, there can be 2 different objects in the database for the same machine. This task merges the duplicate objects and is usually only needed when agents are installed before a computer comes in from AD sync.

### Purge Maintenance - Agent Logs

This server task will remove all Agent Log data that is older than the time period specified.

__Parameters__: Can be set to Seconds, Minutes, Hours, Days, and Weeks. The default is 1 Week.

### Purge Maintenance - Application Control Events

Purges the selected Application Control Event types from the database based upon the time range specified. 

__Parameters__: Event Types to Purge (Application Action Events, Application Justification Events, Application Metering Events, Application Verifier Events).

__Notes__: Only Purge Events that belong to specific policies

### Purge Application Control Events older than [default setting = 30 day(s)]

__Notes__: Depending on policy settings, Application Control Events can pull a large amount of data into the database. Privilege Manager administrators must setup schedules for this task, as needed, to purge old or excessive data from Application Control policies.

### Purge Maintenance - Audit Events

This task will remove audit event records older than the specified time period.

__Parameters__: Purge events older than [default setting = 30 day(s)]

__Notes__: The Audit events mainly pertain to a feature that is only accessible in the Silverlight console. There are a few Security Audit events which may be gathered by Privilege Manager. However, in most Privilege Manager instances, this task should not need to be scheduled.

### Purge Maintenance - Completed File Upload Sessions

This task will remove completed file upload sessions older than the specified time period.

__Parameters__: Purge completed sessions older than [default setting = 1 day(s)]

__Notes__: For versions 10.5 or later, the need to run this task should be significantly reduced since they are now cleaned up as file uploads complete.

### Purge Maintenance - Files Undiscovered

Run this task to delete file resources which have not been discovered by File Inventory, and no agent can be identified to collect information for the files.

__Parameters__: Delete Files that have been undiscoverable for longer than [default setting = 1 week(s)]

__Notes__: This task clear up files with the name "New Loaded Resource" that are older than X days. This can be a helpful task to schedule to remove undiscoverable files from the Event Discovery results (for example, temp files that an installer creates and then deletes).

### Purge Maintenance - Incomplete File Upload Sessions

This task will remove incomplete file upload sessions older than the specified time period.

__Parameters__: Purge incomplete sessions older than [default setting = 2 day(s)]

__Notes__: For versions 10.5 or later, the need to run this task should be significantly reduced since they are now cleaned up as file uploads complete.

### Purge Maintenance - Message History

This server task will remove all Message History data that is older than the time period specified. Message History data tracks all events received by the Privilege Manager Server and is used for informational purposes.

__Parameters__: Delete Message History older than [default setting = 30 day(s)]

__Notes__: This task clears the `[Ams.Resource].[MessageHistory]` table. Use this task to purge that table, if it is excessively large.

### Purge Old Computers

Remove old computers and gauge data for old computers.

### Purge Old Unmanaged AD Computers

This task will delete unmanaged computers imported from Active Directory that have not been updated in X days.
