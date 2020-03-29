[title]: # (Scheduled Registration)
[tags]: # (task)
[priority]: # (5)
# Scheduled Registration

## Scheduled Registration (Windows)

Initiate agent registration with server.

| Parameter | Value |
| ----- | ----- |
| Default Active | Y |
| Command | Check Pending TMS Client Tasks |
| Triggers | Daily at 2:00:00 AM starting Mon Oct 01 2018 (repeating every 4 hours) |
| Targets | All Windows Managed Computers - Internal Network (Target) |
| Conditions | None specified by default |
| Advanced | Allow task to be run on demand |
| (missed) | Run task as soon as possible after a scheduled start is missed |
| (stop) | Stop the task if it run for longer than 5 minute(s). |
| (retry on failure) | not set by default |
| Rule | Default (Do not start a new instance) |
| Agent Sent Size | |
| Agent Received Size | |
| Restrictions | |

## Scheduled Registration - Internet Clients (Windows)

Initiate agent registration with server less frequently than internal clients.

| Parameter | Value |
| ----- | ----- |
| Default Active | Y |
| Command | Check Pending TMS Client Tasks |
| Triggers | Daily at 2:00:00 AM starting Mon Oct 01 2018 (repeating every 4 hours) |
| Targets | All Windows Managed Computers - Internet Client (Target) |
| Conditions | None specified by default |
| Advanced | Allow task to be run on demand |
| (missed) | Run task as soon as possible after a scheduled start is missed |
| (stop) | Stop the task if it run for longer than 5 minute(s). |
| (retry on failure) | not set by default |
| Rule | Default (Do not start a new instance) |
| Agent Sent Size | |
| Agent Received Size | |
| Restrictions | |

## Scheduled Registration (Mac OS)

When this policy is triggered the Agent will attempt (or re-attempt) to register with the server.

| Parameter | Value |
| ----- | ----- |
| Default Active | Y |
| Command | Start TMS Registration |
| Triggers | Daily at 2:00:00 AM starting Mon Oct 01 2018 (repeating every 1 hour for a duration of 24 hours) |
| Targets | All MacOS Managed Computers - Internal Network (Target) |
| Conditions | None specified by default |
| Advanced | Allow task to be run on demand |
| (missed) | Run task as soon as possible after a scheduled start is missed |
| (stop) | Stop the task if it run for longer than 5 minute(s). |
| (retry on failure) | not set by default |
| Rule | Default (Do not start a new instance) |
| Agent Sent Size | |
| Agent Received Size | |
| Restrictions | |

## Scheduled Registration (Linux)

This agent-scheduled task refreshes registration data for the assigned agents.

| Parameter | Value |
| ----- | ----- |
| Default Active | Y |
| Command | Start TMS Registration |
| Triggers | Daily at 2:00:00 AM starting Mon Oct 01 2018 (repeating every 1 hour for a duration of 24 hours) |
| Targets | Linux Computers |
| Conditions | None specified by default |
| Advanced | Allow task to be run on demand |
| (missed) | Run task as soon as possible after a scheduled start is missed |
| (stop) | Stop the task if it run for longer than 5 minute(s). |
| (retry on failure) | not set by default |
| Rule | Default (Do not start a new instance) |
| Agent Sent Size | |
| Agent Received Size | |
| Restrictions | |
