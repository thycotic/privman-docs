[title]: # (List of Default Actions)
[tags]: # (default,out-of-box)
[priority]: # (5999)
# List of Default Actions

This topic describes the out-of-the-box actions that are available in Privilege Manager and can be used to make your policy configuration process easy.

## Actions Catalog  

Here is the complete list of Actions that come with Privilege Manager out-of-the-box, according to category type:  
  
### Adjust Effective Process Rights Action

| Action | Description |
| ----- | ----- |
| __Run as Root__ | Adjust the process rights of the application to run as the root user (MacOS) |

### Adjust Process Rights Action

| Action | Description |
| ----- | ----- |
| __Add Administrative Rights__ | This action adds basic administrative rights needed to install and run specified applications |
| __Add Administrator Rights – Unrestricted__ | This action adds administrative rights at a higher integrity level for specified applications. Usually you will only need to use this type of action if an application or installer needs to create a global object, such as a service, or if system changes require unrestricted administrator rights |
| __Remove Administrator Rights__ | This action removes administrative rights for specified applications |
| __Remove Advanced Privileges Action__ | This action removes advanced privileges for specified applications from the process token |

### Allow Copy Action

| Action | Description |
| ----- | ----- |
| __Allow Copy to/Applications/Directory__ | This action is used by policies that allow users to run the package installer elevated |

### Application Verifier Action

| Action | Description |
| ----- | ----- |
| __Application Compatibility Testing__ | This action triggers application compatibility testing while the process runs and sends the results to the server |

### Apply SVS Layer Action

| Action | Description |
| ----- | ----- |
| __Workspace Virtualization Global Layer__ | This action places specified applications in a common Workspace Virtualization global layer |
| __Workspace Virtualization Isolation Layer__ | This action places specified applications in a common Workspace Virtualization isolation layer |

### Advanced Message (Windows)

| Action | Description |
| ----- | ----- |
| __Application Denied Message Action__ | This action will display a modal denial notification message to the user and prevent application execution on Windows  |
| __Application Denied Notification Action__  | This action will display a notification to the user that the process has been denied by a policy. The notification window will fade in and out and automatically close after a period of time |
| __Approval Request Form Action__ | This action will display an approval request form for approval before allowing application to run  |
| __Authenticated Justification Message Action__ | This action will display a customized message to the user, allowing for feedback and requiring authentication before running an application |
| __Group Member Authenticated Message Action__  | This action will display a customized message to the user and requires authentication by a member of the specified group if the end-user is not a member |
| __Justify Application Elevation Action__ | This action will display a justification prompt to the user before continuing to the process controlled by a policy |
| __Justify Application Message Action__  | This action will display a justification prompt to the user before continuing to the process controlled by a policy |

### De-elevate Child Processes

| Action | Description |
| ----- | ----- |
| __De-elevate Child Processes__ | Ensures that all child processes are created without administrator rights. Forces all new processes created by the targeted application to be launched by a de-elevated token. |

### Deny Actions

| Action | Description |
| ----- | ----- |
| __Deny Execute__ | This action stops specified applications from executing |
| __Deny Read/Write Access to Microsoft Office Document Files__ | This action can be used to deny read and write access to Microsoft Office documents |
| __Deny Windows Hooking__ | This action limits specified applications from interacting in malicious ways with other applications |
| __Deny Write Access to Executable Files__  | This action can be used to deny write access to common executable files |

### Display Advanced Message Actions

| Action | Description |
| ----- | ----- |
| __Application Approval Request Message Action__ | Application Approval Request Message Action for Mac OS |
| __Application Justification Message Action__ | Application Justification Message Action for Mac OS  |
| __Application Denied Message Action__ | This action will display a modal denial notification message to the user and prevent application execution on MacOS |
| __Application Warning Message Action__ | Application Warning Message Action for Mac OS |

### Display User Message - Basic

| Action | Description |
| ----- | ----- |
| __Deny Execute Message__ | This action displays a message to the user informing them that an application has been denied execution |
| __Deny Files Read and Write Access Message__ | This action displays a message to the user informing them that an application will be restricted from certain file access |
| __Limit Process Rights for New Applications Message__ | This action displays a message to the user informing them that an application has had its rights reduced |
| __Quarantine Message__ | This action displays a message to the user informing them that an application has been quarantined  |
| __Remove Rights Message__  | This action displays a message to the user informing them of an associated action |
| __SWV Global Layer User Message__  | This action displays a message to the user informing them that an application has been placed in SWV global layer |
| __SWV Isolation Layer User Message__ | This action displays a message to the user informing them that an application has been placed in SWV isolation layer |
| __Windows Hooking Message__ | This action displays a message to the user informing them that an application will be stopped from interacting with other applications |

### Encrypt Application Files

| Action | Description |
| ----- | ----- |
| __Encrypt Microsoft Office Documents__ | This action can be used to automatically encrypt common application documents using Windows EFS |

### Execute Application Action

| Action | Description |
| ----- | ----- |
| __Immediate File Inventory__ | This action will inventory the file being executed |

### Enable UAC Virtualization

| Action | Description |
| ----- | ----- |
| __Enable UAC Virtualization__ | This action will turn on UAC virtualization for the target process. |

### Meter Application Action

| Action | Description |
| ----- | ----- |
| __Meter Application Usage__ | This action meters the usage of the specified applications |

### Quarantine File Action

| Action | Description |
| ----- | ----- |
| __File Quarantine__ | This action can be used to quarantine a file by moving it to the default agent quarantine path |

### Restrict File Dialogs

| Action | Description |
| ----- | ----- |
| __Restrict File Dialogs__ | This action prevents users from abusing the elevated rights of the application via the file open and save dialogs. This is a recommended action that customers should add to their elevation policies. |

### Set Environment Variable Action

| Action | Description |
| ----- | ----- |
| __Suppress User Account Control Consent Dialog (Legacy)__ | This action will prevent the UAC consent dialog from being displayed. This action should only be used with Agent versions 10.4 and older.  |

### Set Process Security Descriptor

| Action | Description |
| ----- | ----- |
| __Locked down Service Process Security Descriptor__ | This action applies a restrictive security descriptor disallowing Administrators the right to terminate the process |
