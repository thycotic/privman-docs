[title]: # (Local User Inventory Policy)
[tags]: # (task)
[priority]: # (5)
# Local User Inventory Policy

The purpose of this policy is to inventory Local User accounts, groups and group membership on the client. This policy can also be used to inventory specific account privileges.

| Parameter | Value |
| ----- | ----- |
| Default Active | Yes |
| Command | Local Security Inventory Command |
| Triggers | Weekly on Sun at 2:00:00 AM |
| | Upon task creation/modification |
| Targets | All Windows Computers with Local Security Agent Installed (Target) |
| Conditions | None specified by default |
| Advanced | Allow task to be run on demand |
| (missed) | Run task as soon as possible after a scheduled start is missed |
| (stop) | Stop the task if it run for longer than 0 minute(s) - not set by default. |
| (retry on failure) | not set by default |
| Rule | Default (Do not start a new instance) |
| Agent Sent Size | depends on number of users and groups |
| Agent Received Size | n/a |
| Restrictions | GPO - Audit Account Management enabled does not use Security Event Log |

## Local User Inventory Policy (MacOS)

| Parameter | Value |
| ----- | ----- |
| Default Active | Yes |
| Command | Local Security Inventory Command |
| Triggers | Weekly on Sun at 2:00:00 AM |
| | Upon task creation/modification |
| Targets | MacOS Computers |
| Conditions | None specified by default |
| Advanced | Allow task to be run on demand |
| (missed) | Run task as soon as possible after a scheduled start is missed |
| (stop) | Stop the task if it run for longer than 0 minute(s) - not set by default. |
| (retry on failure) | not set by default |
| Rule | Default (Do not start a new instance) |
| Agent Sent Size | depends on number of users and groups |
| Agent Received Size | n/a |
| Restrictions | none |
