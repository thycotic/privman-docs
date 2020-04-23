[title]: # (Set Agent Log Size)
[tags]: # (task)
[priority]: # (5)
# Set Agent Log Size

Configures the size of the Agent Event Log. By default this is set to 1 MB. For most environments it is recommended to increase the Agent Event Log size. This task can be used to override the default setting.

| Parameter | Value |
| ----- | ----- |
| Default Active | No |
| Command | Set Agent Log Size (Windows) |
| Parameters | Log Size: 20 MB |
| Triggers | Daily at 6:00:00 AM |
| Targets | Windows Computers |
| Conditions | None specified by default |
| Advanced | Allow task to be run on demand |
| (missed) | Run task as soon as possible after a scheduled start is missed |
| (stop) | Stop the task if it run for longer than 0 minute(s). - not set by default |
| (retry on failure) | not set by default |
| Rule | Default (Do not start a new instance) |
| Agent Sent Size | n/a |
| Agent Received Size | n/a |
| Restrictions | none |
