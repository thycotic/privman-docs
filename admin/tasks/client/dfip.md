[title]: # (Default File Inventory Policy)
[tags]: # (task)
[priority]: # (5)
# Default File Inventory Policy

The purpose of this policy is to inventory software programs running on the managed computer.

These policies use their respective OS based File Specification filters, which in turn have a set of optional additional filters to identify the programs to be inventoried.

## Default File Inventory Policy (Windows)

| Parameter | Value |
| ----- | ----- |
| Default Active | Yes |
| Command | File Inventory Command |
| Parameters | Default File Specification (Windows) |
| Triggers | Weekly on Sun at 3:00:00 AM |
| Targets | All Windows Computers with File Inventory Agent Installed (Target) |
| Conditions | Idle: None specified by default |
| | Power: Start the task only if the computer is on AC power, Stop if the computer switches to battery power |
| Advanced | Allow task to be run on demand |
| (missed) | Run task as soon as possible after a scheduled start is missed |
| | Stop the task if it run for longer than 3 day(s). |
| (retry on failure) | not set by default |
| Rule | Default (Do not start a new instance) |
| Agent Sent Size | depends on number of programs to inventory |
| Agent Received Size | n/a |
| Restrictions | none |

## Default File Inventory Policy (MacOS)

| Parameter | Value |
| ----- | ----- |
| Default Active | Yes |
| Command | File Inventory Command |
| Parameters | Default File Specification (MacOS), Default App Bundles File Specification Filter |
| Triggers | Weekly on Sun at 3:00:00 AM |
| Targets | All Mac OS Computers with File Inventory Agent Installed (Target) |
| Conditions | Idle: None specified by default |
| | Power: Start the task only if the computer is on AC power, Stop if the computer switches to battery power |
| Advanced | Allow task to be run on demand |
| (missed) | Run task as soon as possible after a scheduled start is missed |
| | Stop the task if it run for longer than 3 day(s). |
| (retry on failure) | not set by default |
| Rule | Default (Do not start a new instance) |
| Agent Sent Size | depends on number of programs to inventory |
| Agent Received Size | n/a |
| Restrictions | none |
