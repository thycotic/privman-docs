[title]: # (Configure PM Remove Programs)
[tags]: # (task)
[priority]: # (5)
# Configure Privilege Manager Remove Programs

Configure the [Privilege Manager Remove Programs](../../../how-to/maintenance/remove-programs-utility.md) behavior.

For standard users the utility by default,

* adds all programs to the Control Panel.
* hides repair options for all installers.
* shows the blocked installer list.
* prevents Thycotic software from being uninstalled.

| Parameter | Value |
| ----- | ----- |
| Default Active | Yes |
| Command | Configure Remove Programs Application |
| Parameters | selected: Add to Control Panel, Hide Repair for All Installers, Show Blocked Installers in List, Vendor software that can't be Uninstalled: Thycotic. |
| Triggers | Daily at 10:00:00 PM (repeating every 2 hours for a duration of 24 hours) |
| | Upon task creation/modification |
| Targets | Windows Computers |
| Conditions | None specified by default |
| Advanced | Allow task to be run on demand |
| (missed) | Run task as soon as possible after a scheduled start is missed |
| | Stop the task if it run for longer than 3 day(s). |
| (retry on failure) | not set by default |
| Rule | Default (Do not start a new instance) |
| Agent Sent Size | n/a |
| Agent Received Size | n/a |
| Restrictions | none |
