[title]: # (Perform Resource Discovery)
[tags]: # (task)
[priority]: # (5)
# Perform Resource Discovery

Schedule on which agents check with server to determine, if any local resources require discovery.

After any type of resource discovery, it might be possible that the server does not have all the details required to correctly identify what was initially provided by the agent. The agent periodically checks in with the server, if any additional information needs to be discovered. The sever then sends information back to the agent about any pending item clarifications.

## Perform Resource Discovery (Windows)

| Parameter | Value |
| ----- | ----- |
| Default Active | Yes |
| Command | Resource Discovery Command |
| Triggers | Daily at 12:00:00 AM (repeating every 4 hours for a duration of 24 hours) |
| | Upon task creation/modification |
| Targets | Windows Computers |
| Conditions | None specified by default |
| Advanced | Allow task to be run on demand |
| (missed) | Run task as soon as possible after a scheduled start is missed |
| (stop) | Stop the task if it run for longer than 1 hour. |
| (retry on failure) | not set by default |
| Rule | Default (Do not start a new instance) |
| Agent Sent Size | depends on server request |
| Agent Received Size | depends on request volume and the number of items pending on server for clarification |
| Restrictions | none |

## Perform Resource Discovery (Mac OS)

| Parameter | Value |
| ----- | ----- |
| Default Active | Yes |
| Command | Resource Discovery Command |
| Triggers | Daily at 3:00:00 AM (repeating every 4 hours for a duration of 24 hours) |
| | Upon task creation/modification |
| Targets | MacOS Computers |
| Conditions | Idle: None specified by default |
| | Power: Start the task only if the computer is on AC power, Stop if the computer switches to battery power |
| Advanced | Allow task to be run on demand |
| (missed) | Run task as soon as possible after a scheduled start is missed |
| (stop) | Stop the task if it run for longer than 3 day(s). |
| (retry on failure) | not set by default |
| Rule | Default (Do not start a new instance) |
| Agent Sent Size | depends on server request |
| Agent Received Size | depends on request volume and the number of items pending on server for clarification |
| Restrictions | none |
