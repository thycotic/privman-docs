[title]: # (Cleanup Agent Inventory Transfer)
[tags]: # (task)
[priority]: # (5)
# Cleanup Agent Inventory Transfer

Completes and cleans BITS transfers and temporary files used by the TMS Agent Inventory Helper.

## Cleanup Agent Inventory Transfers (Windows)

| Parameter | Value |
| ----- | ----- |
| Default Active | Y |
| Command | Cleanup Agent Inventory Transfers |
| Parameters | n/a |
| Triggers | Daily at 2:00:02 AM starting Thu Jan 01 2015 |
| Targets | All Windows Computers with Application Control Agent Installed (Target) |
| Conditions | None specified by default |
| Advanced | Allow task to be run on demand |
| (missed) | Run task as soon as possible after a scheduled start is missed |
| | Stop the task if it run for longer than 30 minutes. |
| (retry on failure) | not set by default |
| Rule | Default (Do not start a new instance) |
| Agent Sent Size | |
| Agent Received Size | |
| Restrictions | |
