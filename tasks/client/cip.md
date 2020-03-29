[title]: # (COM Inventory Policy)
[tags]: # (task)
[priority]: # (5)
# COM Inventory Policy

The purpose of this policy is to inventory COM+ and DCOM packages installed on the client.

| Parameter | Value |
| ----- | ----- |
| Default Active | N |
| Command | Local Security COM Inventory Command |
| Triggers | Weekly on Sun at 2:00:00 AM starting Tue Jan 01 2013 |
| | Upon task creation/modification |
| Targets | All Windows Computers with Local Security Agent Installed (Target) |
| Conditions | None specified by default |
| Advanced | Allow task to be run on demand |
| (missed) | Run task as soon as possible after a scheduled start is missed |
| (stop) | Stop the task if it run for longer than 0 minute(s) - not set by default. |
| (retry on failure) | not set by default |
| Rule | Default (Do not start a new instance) |
| Agent Sent Size | |
| Agent Received Size | |
| Restrictions | |
