[title]: # (Cleanup sent PM Events)
[tags]: # (task)
[priority]: # (5)
# Cleanup Sent Privilege Manager Events

Purges Agent events that have been successfully transmitted from managed endpoints to reclaim disk space.

## Cleanup sent Privilege Manager Events (Windows)

| Parameter | Value |
| ----- | ----- |
| Default Active | Yes |
| Command | Remove sent TMS Client Events (Windows) |
| Triggers | Daily at 2:00:02 AM |
| Targets | Windows Computers |
| Conditions | None specified by default |
| Advanced | Allow task to be run on demand |
| (missed) | Run task as soon as possible after a scheduled start is missed |
| | Stop the task if it run for longer than 30 minutes. |
| (retry on failure) | not set by default |
| Rule | Default (Do not start a new instance) |
| Agent Sent Size | n/a |
| Agent Received Size | n/a |
| Restrictions | none |

## Cleanup sent Privilege Manager Events (Mac OS)

| Parameter | Value |
| ----- | ----- |
| Default Active | Yes |
| Command | Remove sent TMS Client Events (MacOS) |
| Triggers | Daily at 2:30:02 AM |
| Targets | MacOS Computers |
| Conditions | None specified by default |
| Advanced | Allow task to be run on demand |
| (missed) | Run task as soon as possible after a scheduled start is missed |
| | Stop the task if it run for longer than 30 minutes. |
| (retry on failure) | not set by default |
| Rule | Default (Do not start a new instance) |
| Agent Sent Size | n/a |
| Agent Received Size | n/a |
| Restrictions | none |
