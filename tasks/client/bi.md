[title]: # (Basic Inventory)
[tags]: # (task)
[priority]: # (5)
# Basic Inventory

## Basic Inventory (Initial, Windows)

Instructs computers to report the Win32_ComputerSystem, Win32_ComputerSystemProduct and Win32_OperatingSystem WMI classes to the server. 

| Parameter | Value |
| ----- | ----- |
| Default Active | Y |
| Command | Perform WMI Basic Inventory (Windows) |
| Parameters | WMI classes: ROOT\CIMV2:WIN32_ComputerSystemProduct ROOT\CIMV2:Win32_ComputerSystem ROOT\CIMV2:Win32_OperatingSystem |
| Triggers | Daily at 10:00:00 AM starting Mon Oct 01 2018 |
| | Upon task creation/modification |
| Targets | All Windows Managed Computers - No Basic Inventory (Target) |
| Conditions | None specified by default |
| Advanced | Allow task to be run on demand |
| (missed) | Run task as soon as possible after a scheduled start is missed |
| | Stop the task if it run for longer than 5 minutes. |
| (retry on failure) | not set by default |
| Rule | Default (Do not start a new instance) |
| Agent Sent Size | |
| Agent Received Size | |
| Restrictions | |


## Basic Inventory (Windows)

Instructs computers to report the

* Win32_ComputerSystem,
* Win32_ComputerSystemProduct, and
* Win32_OperatingSystem WMI classes to the server.

| Parameter | Value |
| ----- | ----- |
| Default Active | Y |
| Command | Perform WMI Basic Inventory (Windows) |
| Parameters | WMI classes: ROOT\CIMV2:WIN32_ComputerSystemProduct, ROOT\CIMV2:Win32_ComputerSystem, ROOT\CIMV2:Win32_OperatingSystem |
| Triggers | Daily at 8:00:00 AM starting Mon Oct 01 2018 |
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

This scheduled task triggers the Agent to send Mac OS basic inventory.

| Parameter | Value |
| ----- | ----- |
| Default Active | Y |
| Command | Perform Basic Inventory (MacOS) |
| Triggers | Daily at 10:00:00 AM starting Mon Oct 01 2018 |
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
| Default Active | Y |
| Command | Perform Basic Inventory (MacOS) |
| Triggers | Daily at 10:00:00 AM starting Mon Oct 01 2018 |
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
