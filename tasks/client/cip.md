[title]: # (COM Inventory Policy)
[tags]: # (task)
[priority]: # (5)
# COM Inventory Policy

The purpose of this policy is to inventory COM+ and DCOM packages installed on the client. The inventory of these package

COM+ (Component Object Model) and DCOM (Distributed Component Object Model) utilize RPC calls for component communication and access to the object's methods and data. Running an inventory on those packages on a client is beneficial, if apps using those packages require elevation or should be denied.

| Parameter | Value |
| ----- | ----- |
| Default Active | No |
| Command | Local Security COM Inventory Command |
| Triggers | Weekly on Sun at 2:00:00 AM |
| | Upon task creation/modification |
| Targets | All Windows Computers with Local Security Agent Installed (Target) |
| Conditions | None specified by default |
| Advanced | Allow task to be run on demand |
| (missed) | Run task as soon as possible after a scheduled start is missed |
| (stop) | Stop the task if it run for longer than 0 minute(s) - not set by default. |
| (retry on failure) | not set by default |
| Rule | Default (Do not start a new instance) |
| Agent Sent Size | depends on number of COM+ and DCOM packages |
| Agent Received Size | n/a |
| Restrictions | none |
