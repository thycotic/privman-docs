[title]: # (Update Applicable Policies)
[tags]: # (task)
[priority]: # (5)
# Update Applicable Policies

## Update Applicable Policies (Windows)

Instructs Agent to check with server for policy changes.

| Parameter | Value |
| ----- | ----- |
| Default Active | Yes |
| Command | Update Applicable Policies |
| Triggers | Daily at 12:00:00 AM (repeating every 30 minutes for a duration of 24 hours) |
| Targets | All Windows Managed Computers - Internal Network (Target) |
| Conditions | None specified by default |
| Advanced | On: Allow task to be run on demand |
| | On: Run task as soon as possible after a scheduled start is missed |
| | Off: If the task fails, attempt to restart |
| | On: Stop the task if it runs for longer than 5 minute(s). |
| Rule | Default (Do not start a new instance) |
| Agent Sent Size | |
| Agent Received Size | |
| Restrictions | none |

## Update Applicable Policies - Internet Clients (Windows)

Instructs Agent to check with server for policy changes less frequently than internal clients.

| Parameter | Value |
| ----- | ----- |
| Default Active | Yes |
| Command | Update Applicable Policies |
| Triggers | Daily at 12:00:00 AM (repeating every 2 hours for a duration of 24 hours) |
| Targets | All Windows Managed Computers - Internet Client (Target) |
| Conditions | None specified by default |
| Advanced | On: Allow task to be run on demand |
| | On: Run task as soon as possible after a scheduled start is missed |
| | Off: If the task fails, attempt to restart |
| | On: Stop the task if it runs for longer than 5 minute(s). |
| Rule | Default (Do not start a new instance) |
| Agent Sent Size | |
| Agent Received Size | |
| Restrictions | none |

## Update Applicable Policies (Mac OS)

When this policy is triggered the Agent will check the server for updated policies.

| Parameter | Value |
| ----- | ----- |
| Default Active | Yes |
| Command | Update Applicable Policies |
| Triggers | Daily at 12:00:00 AM (repeating every 30 minutes for a duration of 24 hours) |
| Targets | All MacOS Managed Computers - Internal Network (Target) |
| Conditions | None specified by default |
| Advanced | On: Allow task to be run on demand |
| | On: Run task as soon as possible after a scheduled start is missed |
| | Off: If the task fails, attempt to restart |
| | On: Stop the task if it runs for longer than 5 minute(s). |
| Rule | Default (Do not start a new instance) |
| Agent Sent Size | |
| Agent Received Size | depends on the number of updated policies |
| Restrictions | none |

## Update Applicable Policies (Unix/Linux)

This remote-scheduled command will update policies applicable to the assigned agents.

| Parameter | Value |
| ----- | ----- |
| Default Active | Yes |
| Command | Update Applicable Policies |
| Triggers | Daily at 12:00:00 AM (repeating every 2 hours for a duration of 24 hours) |
| Targets | Unix/Linux Computers |
| Deployment | The deployment status of this policy, if this number is 0 or incorrect, then the Resource and Collection Targeting Update Task might need to run.
| Conditions | None specified by default |
| Advanced | On: Allow task to be run on demand |
| | On: Run task as soon as possible after a scheduled start is missed |
| | Off: If the task fails, attempt to restart |
| | On: Stop the task if it runs for longer than 5 minute(s). |
| Rule | Default (Do not start a new instance) |
| Agent Sent Size | |
| Agent Received Size | |
| Restrictions | none |
