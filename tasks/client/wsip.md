[title]: # (Windows Server Inventory Policy)
[tags]: # (task)
[priority]: # (5)
# Windows Server Inventory Policy

The purpose of this policy is to inventory Windows Services on the client.

| Parameter | Value |
| ----- | ----- |
| Default Active | Yes |
| Command | Local Security Service Inventory Command |
| Triggers | Weekly on Sun at 2:00:00 AM |
| | Upon task creation/modification |
| Targets | All Windows Computers with Local Security Agent Installed (Target) |
| Conditions | None specified by default |
| Advanced | Allow task to be run on demand |
| (missed) | Run task as soon as possible after a scheduled start is missed |
| (stop) | Stop the task if it run for longer than 0 minute(s). - not set by default |
| (retry on failure) | not set by default |
| Rule | Default (Do not start a new instance) |
| Agent Sent Size | depends on number of installed windows services |
| Agent Received Size | n/a |
| Restrictions | none |
