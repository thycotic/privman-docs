[title]: # (Ensure UAC Override Setting)
[tags]: # (task)
[priority]: # (5)
# Ensure UAC Override Setting (Windows)

Ensures that the UAC Override Registry Key is set.

<!-- TODO: What happens... When to use... Why to use... -->

| Parameter | Value |
| ----- | ----- |
| Default Active | Yes |
| Command | Ensure UAC Override Registry Key |
| Parameters | Default File Specification (Windows) |
| Triggers | Daily at 12:00:00 AM |
| | At startup |
| Targets | 10.8: Windows Computers |
| | Legacy: All Windows Computers with Application Control Agent Installed (Target) |
| Conditions | None specified by default |
| Advanced | Allow task to be run on demand |
| (missed) | Run task as soon as possible after a scheduled start is missed |
| | Stop the task if it run for longer than 15 minute(s). |
| (retry on failure) | not set by default |
| Rule | Default (Do not start a new instance) |
| Agent Sent Size | n/a |
| Agent Received Size | n/a |
| Restrictions | none |
