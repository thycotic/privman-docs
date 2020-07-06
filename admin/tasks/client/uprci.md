[title]: # (Update Provisioned Resource Client Items)
[tags]: # (task)
[priority]: # (5)
# Update Provisioned Resource Client Items

These policies trigger the Agent to force a Client Item Update for provisioned resources on the specific client system.

## Update Provisioned Resource Client Items (Windows)

| Parameter | Value |
| ----- | ----- |
| Default Active | Yes |
| Command | Force Client Item Update Command |
| Parameters | Category: Provisioned Resource |
| Triggers | Daily at 8:00:00 AM starting Sun Apr 07 2013 |
| Targets | All Windows Computers with Local Security Agent Installed (Target) |
| Conditions | None specified by default |
| Advanced | Allow task to be run on demand |
| (missed) | Run task as soon as possible after a scheduled start is missed |
| (stop) | Stop the task if it run for longer than 0 minute(s). - not set by default |
| (retry on failure) | not set by default |
| Rule | Default (Do not start a new instance) |
| Agent Sent Size | depends on the number of provisioned items |
| Agent Received Size | n/a |
| Restrictions | none |

## Update Provisioned Resource Client Items (MacOS)

| Parameter | Value |
| ----- | ----- |
| Default Active | Yes |
| Command | Force Client Item Update Command |
| Parameters | Category: Provisioned Resource |
| Triggers | Daily at 8:00:00 AM starting Sun Apr 07 2013 |
| Targets | All MacOS Computers with Local Security Agent Installed (Target) |
| Conditions | None specified by default |
| Advanced | Allow task to be run on demand |
| (missed) | Run task as soon as possible after a scheduled start is missed |
| (stop) | Stop the task if it run for longer than 0 minute(s). - not set by default |
| (retry on failure) | not set by default |
| Rule | Default (Do not start a new instance) |
| Agent Sent Size | depends on the number of provisioned items |
| Agent Received Size | n/a |
| Restrictions | none |
