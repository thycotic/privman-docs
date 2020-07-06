[title]: # (Shared Folder Inventory Policy)
[tags]: # (task)
[priority]: # (5)
# Shared Folder Iventory Policy

The purpose of this policy is to inventory shared folders on the client.

| Parameter | Value |
| ----- | ----- |
| Default Active | No |
| Command | Local Security Shared Folder Inventory Command |
| Triggers | Weekly on Sun at 2:00:00 AM |
| Targets | All Windows Computers with Local Security Agent Installed (Target) |
| Conditions | None specified by default |
| Advanced | Allow task to be run on demand |
| (missed) | Run task as soon as possible after a scheduled start is missed |
| (stop) | Stop the task if it run for longer than 0 minute(s). - not set by default |
| (retry on failure) | not set by default |
| Rule | Default (Do not start a new instance) |
| Agent Sent Size | depends on number of shared folders on the endpoint |
| Agent Received Size | n/a |
| Restrictions | none |
