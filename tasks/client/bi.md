[title]: # (Basic Inventory)
[tags]: # (task)
[priority]: # (5)
# Basic Inventory

todo

Trigger Advanced schedule

## Basic Inventory (Initial, Windows)

Instructs computers to report the following WMI classes to the server at initial start-up:

* Win32_ComputerSystem,
* Win32_ComputerSystemProduct
* Win32_OperatingSystem WMI

| Parameter | Value |
| ----- | ----- |
| Default Active | Yes |
| Command | Perform WMI Basic Inventory (Windows) |
| Parameters | WMI classes: `ROOT\CIMV2:WIN32_ComputerSystemProduct` `ROOT\CIMV2:Win32_ComputerSystem` `ROOT\CIMV2:Win32_OperatingSystem` |
| Triggers | Daily at 10:00:00 AM |
| | Upon task creation/modification |
| Targets | All Windows Managed Computers - No Basic Inventory (Target) |
| Conditions | None specified by default |
| Advanced | Allow task to be run on demand |
| (missed) | Run task as soon as possible after a scheduled start is missed |
| | Stop the task if it run for longer than 5 minutes. |
| (retry on failure) | not set by default |
| Rule | Default (Do not start a new instance) |
| Agent Sent Size | 250 KB |
| Agent Received Size | n/a |
| Restrictions | none |

## Basic Inventory (Windows)

Instructs computers to report the following WMI classes to the server:

* Win32_ComputerSystem,
* Win32_ComputerSystemProduct
* Win32_OperatingSystem WMI

| Parameter | Value |
| ----- | ----- |
| Default Active | Yes |
| Command | Perform WMI Basic Inventory (Windows) |
| Parameters | WMI classes: ROOT\CIMV2:WIN32_ComputerSystemProduct, ROOT\CIMV2:Win32_ComputerSystem, ROOT\CIMV2:Win32_OperatingSystem |
| Triggers | Daily at 8:00:00 AM |
| Targets | Windows Computers |
| Conditions | None specified by default |
| Advanced | Allow task to be run on demand |
| (missed) | Run task as soon as possible after a scheduled start is missed |
| | Stop the task if it run for longer than 5 minutes. |
| (retry on failure) | not set by default |
| Rule | Default (Do not start a new instance) |
| Agent Sent Size | |
| Agent Received Size | |
| Restrictions | |

## Basic Inventory (Initial, Mac OS)

This scheduled task triggers the Agent to send the initial Mac OS basic inventory.

| Parameter | Value |
| ----- | ----- |
| Default Active | Yes |
| Command | Perform Basic Inventory (MacOS) |
| Triggers | Daily at 10:00:00 AM |
| | Upon task creation/modification |
| Targets | All MacOS Managed Computers - No Basic Inventory (Target) |
| Conditions | None specified by default |
| Advanced | Allow task to be run on demand |
| (missed) | Run task as soon as possible after a scheduled start is missed |
| | Stop the task if it run for longer than 5 minutes. |
| (retry on failure) | not set by default |
| Rule | Default (Do not start a new instance) |
| Agent Sent Size | |
| Agent Received Size | |
| Restrictions | |

## Basic Inventory (Mac OS)

This scheduled task triggers the Agent to send Mac OS basic inventory.

| Parameter | Value |
| ----- | ----- |
| Default Active | Yes |
| Command | Perform Basic Inventory (MacOS) |
| Triggers | Daily at 10:00:00 AM |
| Targets | MacOS Computers |
| Conditions | None specified by default |
| Advanced | Allow task to be run on demand |
| (missed) | Run task as soon as possible after a scheduled start is missed |
| | Stop the task if it run for longer than 5 minutes. |
| (retry on failure) | not set by default |
| Rule | Default (Do not start a new instance) |
| Agent Sent Size | |
| Agent Received Size | |
| Restrictions | |
