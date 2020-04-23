[title]: # (Update Agent Commands)
[tags]: # (task)
[priority]: # (5)
# Update Agent Commands

Task sends up request for hashes of specific client item types. With Privilege Manager version 10.7 and up returned items are filters based on the last time run the task ran.

## Update Agent Commands (Windows)

Instructs Agent to update any agent commands if required.

| Parameter | Value |
| ----- | ----- |
| Default Active | Yes |
| Command | Force Client Item Update Command |
| Parameters | Category: Agent Command |
| Triggers | Daily at 12:00:00 AM |
| Targets | Windows Computers |
| Conditions | None specified by default |
| Advanced | Allow task to be run on demand |
| (missed) | Run task as soon as possible after a scheduled start is missed |
| (stop) | Stop the task if it run for longer than 10 minute(s). |
| (retry on failure) | not set by default |
| Rule | Default (Do not start a new instance) |
| Agent Sent Size | |
| Agent Received Size | |
| Restrictions | none |

## Update Agent Commands (Mac OS)

When this policy is triggered the Agent will update agent command items.

| Parameter | Value |
| ----- | ----- |
| Default Active | Yes |
| Command | Force Client Item Update Command |
| Parameters | Category: Agent Command |
| Triggers | Daily at 12:00:00 AM |
| Targets | MacOS Computers |
| Conditions | None specified by default |
| Advanced | Allow task to be run on demand |
| (missed) | Run task as soon as possible after a scheduled start is missed |
| (stop) | Stop the task if it run for longer than 10 minute(s). |
| (retry on failure) | not set by default |
| Rule | Default (Do not start a new instance) |
| Agent Sent Size | |
| Agent Received Size | depends on the number of updated commands |
| Restrictions | none |
