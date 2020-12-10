[title]: # (Scheduled Registration)
[tags]: # (task)
[priority]: # (5)
# Scheduled Registration

## Scheduled Registration (Windows)

Initiate agent registration with server.

| Parameter | Value |
| ----- | ----- |
| Default Active | Yes |
| Command | Check Pending TMS Client Tasks |
| Triggers | Daily at 2:00:00 AM (repeating every 4 hours) |
| Targets | All Windows Managed Computers - Internal Network (Target) |
| Conditions | None specified by default |
| Advanced | On: Allow task to be run on demand |
| | On: Run task as soon as possible after a scheduled start is missed |
| | Off: If the task fails, attempt to restart |
| | On: Stop the task if it runs for longer than 5 minute(s). |
| Rule | Default (Do not start a new instance) |
| Agent Sent Size | 5 KB |
| Agent Received Size | n/a |
| Restrictions | none |

## Scheduled Registration - Internet Clients (Windows)

Initiate agent registration with server less frequently than internal clients.

| Parameter | Value |
| ----- | ----- |
| Default Active | Yes |
| Command | Check Pending TMS Client Tasks |
| Triggers | Daily at 2:00:00 AM (repeating every 4 hours) |
| Targets | All Windows Managed Computers - Internet Client (Target) |
| Conditions | None specified by default |
| Advanced | On: Allow task to be run on demand |
| | On: Run task as soon as possible after a scheduled start is missed |
| | Off: If the task fails, attempt to restart |
| | On: Stop the task if it runs for longer than 5 minute(s). |
| Rule | Default (Do not start a new instance) |
| Agent Sent Size | 5 KB |
| Agent Received Size | n/a |
| Restrictions | none |

## Scheduled Registration (Mac OS)

When this policy is triggered the Agent will attempt (or re-attempt) to register with the server.

| Parameter | Value |
| ----- | ----- |
| Default Active | Yes |
| Command | Start TMS Registration |
| Triggers | Daily at 2:00:00 AM (repeating every 1 hour for a duration of 24 hours) |
| Targets | All MacOS Managed Computers - Internal Network (Target) |
| Conditions | None specified by default |
| Advanced | On: Allow task to be run on demand |
| | On: Run task as soon as possible after a scheduled start is missed |
| | Off: If the task fails, attempt to restart |
| | On: Stop the task if it runs for longer than 5 minute(s). |
| Rule | Default (Do not start a new instance) |
| Agent Sent Size | 5 KB |
| Agent Received Size | n/a |
| Restrictions | none |

## Scheduled Registration (Unix/Linux)

This agent-scheduled task refreshes registration data for the assigned agents.

| Parameter | Value |
| ----- | ----- |
| Default Active | Yes |
| Command | Start TMS Registration |
| Triggers | Daily at 2:00:00 AM (repeating every 1 hour for a duration of 24 hours) |
| Targets | Unix/Linux Computers |
| Deployment | The deployment status of this policy, if this number is 0 or incorrect, then the Resource and Collection Targeting Update Task might need to run.
| Conditions | None specified by default |
| Advanced | On: Allow task to be run on demand |
| | On: Run task as soon as possible after a scheduled start is missed |
| | Off: If the task fails, attempt to restart |
| | On: Stop the task if it runs for longer than 5 minute(s). |
| Rule | Default (Do not start a new instance) |
| Agent Sent Size | 5 KB |
| Agent Received Size | n/a |
| Restrictions | none |
