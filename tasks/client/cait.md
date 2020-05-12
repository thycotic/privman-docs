[title]: # (Cleanup Agent Inventory Transfer)
[tags]: # (task)
[priority]: # (5)
# Cleanup Agent Inventory Transfer

Completes and cleans BITS transfers and temporary files used by the TMS Agent Inventory Helper.

## Cleanup Agent Inventory Transfers (Windows)

| Parameter | Value |
| ----- | ----- |
| Default Active | Yes |
| Command | Cleanup Agent Inventory Transfers |
| Triggers | Daily at 2:00:02 AM |
| Targets | 10.8: Windows Computers |
| | Legacy: All Windows Computers with Application Control Agent Installed (Target) |
| Conditions | None specified by default |
| Advanced | Allow task to be run on demand |
| (missed) | Run task as soon as possible after a scheduled start is missed |
| | Stop the task if it run for longer than 30 minutes. |
| (retry on failure) | not set by default |
| Rule | Default (Do not start a new instance) |
| Agent Sent Size | depends on number of failed file transfers |
| Agent Received Size | n/a |
| Restrictions | none |
