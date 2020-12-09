[title]: # (Exclusion Path)
[tags]: # (computer groups)
[priority]: # (2)
# Exclusion Path

The Agent Configuration policy can be customized to exclude specified folder paths from all application control policy processing.

All application launched from the specified paths will no be processed via the Privilege Manager agent, which allows for minimal interruption and maximum performance.

Any log entries are executed asynchronously without any impact on processing.

To add an exclusion path to the Agent Configuration policy:

1. Navigate your Computer Group and select __Agent Configuration__.
1. Click __More__ and select __View XML__.
1. Click __Edit__.
1. Navigate to line 42 in the xml data and insert the `<PathExclusions>` block with the path wrapped in an argument of type string `<arr:string>. For example the following block should cause the exclusion of _notepad.exe_  from processing.

   ```xml
        <PathExclusions>
            <arr:string>C:\Windows\System32\notepad.exe</arr:string>
        </PathExclusions>
   ```
1. Click __Import__.
1. Click __Save Changes__.

## Verification

At the endpoint use the [Agent Utility](../utility.md) to make sure the policies are updated. Launch the application you specified in the exclusion, for out example _notepad.exe_ and verify that the [Agent Utility logs](../utility.md#view_logs) contain a message like this:

`Ignoring process 11452 (C:\Windows\System32\notepad.exe) exclusion: c:\windows\system32\notepad.exe`
