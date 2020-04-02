[title]: # (Retry Errored TMS Events)
[tags]: # (task)
[priority]: # (5)
# Retry Errored TMS Events

Scan Agent queue for any events that require retransmission.

## Retry errored TMS Events (Windows)

| Parameter | Value |
| ----- | ----- |
| Default Active | Yes |
| Command | Retry errored TMS Client Events (Windows) |
| Parameters | Force Resending (incl. transient errors) |
| Triggers | Daily at 2:00:02 AM |
| Targets | Windows Computers |
| Conditions | None specified by default |
| Advanced | Allow task to be run on demand |
| (missed) | Run task as soon as possible after a scheduled start is missed |
| (stop) | Stop the task if it run for longer than 1 hour(s). |
| (retry on failure) | not set by default |
| Rule | Default (Do not start a new instance) |
| Agent Sent Size | depends on number of items that require retransmission |
| Agent Received Size | n/a |
| Restrictions | none |

## Retry errored TMS Events (Mac OS)

| Parameter | Value |
| ----- | ----- |
| Default Active | Yes |
| Command | Retry errored TMS Client Events (MacOS) |
| Triggers | Daily at 2:00:02 AM |
| Targets | MacOS Computers |
| Conditions | None specified by default |
| Advanced | Allow task to be run on demand |
| (missed) | Run task as soon as possible after a scheduled start is missed |
| (stop) | Stop the task if it run for longer than 1 hour(s). |
| (retry on failure) | not set by default |
| Rule | Default (Do not start a new instance) |
| Agent Sent Size | depends on number of items that require retransmission |
| Agent Received Size | n/a |
| Restrictions | none |
