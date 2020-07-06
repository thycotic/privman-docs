[title]: # (Scheduled Check for Pending Tasks)
[tags]: # (task)
[priority]: # (5)
# Scheduled Check for Pending Tasks

## Scheduled Check Pending Client Tasks - Internet Clients (Windows)

Initiate a check for pending client tasks. Used by agents that are unable to receive an incoming connection from the server.

| Parameter | Value |
| ----- | ----- |
| Default Active | Yes |
| Command | Check Pending TMS Client Tasks |
| Triggers | Daily at 2:00:00 AM (repeating every 4 hours) |
| Targets | All Windows Managed Computers - Internet Client (Target) |
| Conditions | None specified by default |
| Advanced | Allow task to be run on demand |
| (missed) | Run task as soon as possible after a scheduled start is missed |
| (stop) | Stop the task if it run for longer than 5 minute(s). |
| (retry on failure) | not set by default |
| Rule | Default (Do not start a new instance) |
| Agent Sent Size | n/a |
| Agent Received Size | depends on number of pending items |
| Restrictions | none |

<!-- ## Scheduled Check for Pending Tasks (Linux)

This remote-scheduled task checks for server-scheduled tasks assigned to the agent.

| Parameter | Value |
| ----- | ----- |
| Default Active | Yes |
| Command | Check Pending TMS Client Tasks |
| Triggers | Daily at 2:00:00 AM (repeating every 15 minutes for a duration of 24 hours) |
| Targets | Linux Computers |
| Conditions | None specified by default |
| Advanced | Allow task to be run on demand |
| (missed) | Run task as soon as possible after a scheduled start is missed |
| (stop) | Stop the task if it run for longer than 5 minute(s). |
| (retry on failure) | not set by default |
| Rule | Default (Do not start a new instance) |
| Agent Sent Size | n/a |
| Agent Received Size | depends on number of pending items |
| Restrictions | none |
-->
