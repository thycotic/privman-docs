[title]: # (Launching Executables)
[tags]: # (task)
[priority]: # (6001)
# Tasks Launching Executables

When a task is used to launch executables, but the task does not have an associated user context, the appropriate user token cannot be assigned. This applies to systems with 10.7 and above agents.

## Example Scenario

A scheduled task launches an executable, which requires elevation, for example running the performance monitor process. That task is then set to run with elevated permissions, however not as a specific user, but rather as a local user group. Such task used in a policy will cause the executable to fail, since a specific user token cannot be associated.

## Workaround

If you don't have a user context to assign to a task for launching an executable, you can use a PowerShell script in combination with the task and policy.

1. Create a PowerShell script to launch the executable.
1. Set the task to launch powershell.exe.
1. Pass in the name of the script.
1. Set the your policy to target that script.
