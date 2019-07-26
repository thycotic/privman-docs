[title]: # (List of Actions)
[tags]: # (overview,out-of-box)
[priority]: # (5701)
# List of Actions

This topic describes the out-of-the-box actions that are available in Privilege Manager and can be used to make your policy configuration process easy.

When creating new actions in Privilege Manager, these are the list of category options you may use:

* ActiveX Installer

  This type of action is a specific use-case for older Windows systems (Windows XP and Windows Server 2003). The ActiveX installer action allows or denies an application to enable standard users to install approved ActiveX components. If you don’t know what ActiveX means, you won’t need to use this type of action.

* Adjust Process Rights

  This type of action will add or remove administrator rights. You can remove administrator rights from applications like web browsers to increase their locked-down state for both administrators and standard users.

* Application Classification

  This type of action will restrict applications from modifying certain items and will enforce standard Windows ACLs when the targeted application accesses restricted files, folders, registry keys, or services on a computer.

* Apply Application Compatibility Fix Action

  This type of action will allow old applications that must be run via compatibility mode to execute  without manual compatibility adjustments.

* Deny File Access

  As the name suggests, this type of action will prevent applications from reading or writing (or both) to certain directories or to Microsoft Office documents.

* Deny Windows Hooking

  This type of action will limit specified  applications from interacting in malicious ways with other applications.

* Display Advanced Message

  Display messages are paired with another action type. They are customizable and serve to tell the end user what is happening and why. Advanced messages pop up in the middle of the screen, whereas Basic User messages appear as smaller pop-ups directly from the taskbar area.

* Display User Message (Basic)

  Display messages are paired with another action type. They are customizable and serve to tell the end user what is happening and why. Advanced messages pop up in the middle of the screen, whereas Basic User messages appear as smaller pop-ups directly from the taskbar area.

* Encrypt Application Files

  This type of action will force applications to use Microsoft encryption when saving a file.

* Enhanced Mitigation (EMET) Action

  This action can be used on Endpoints that have the Enhanced Mitigation Experience Toolkit installed. The action will enforce an EMET on the targeted application(s).

* Execute Application

  This type of action will execute another application and (optionally) wait on that process to complete before the original process can execute.

* Sandbox Action

  This type of action will limit the environments in which certain code can execute. The sandbox runs a process in a job object that limits its ability to interact with other processes, as well as limiting some specific types of interactions with the operating system.

* Set Environment Variable Action

  This type of action sets an environment variable for processes that could change the behavior of an  application, or be caught by an Environment Variable filter in another policy.

* Set Process Security Descriptor Action

  Adjusting Process Security allows a process to be protected from most tampering by users. For example,  adjusting process security can restrict who can stop a process from the task manager.

## Actions Catalog  

Here is the complete list of Actions that come with Privilege Manager out-of-the-box, according to category type:  
  
### Adjust Effective Process Rights Action

| Action | Description |
|---|---|
| __Run as Root__ | Adjust the process rights of the application to run as the root user (MacOS) |

### Adjust Process Rights Action

| Action | Description |
|---|---|
| __Add Administrative Rights__ | This action adds basic administrative rights needed to install and run specified applications |
| __Add Administrator Rights – Unrestricted__ | This action adds administrative rights at a higher integrity level for specified applications. Usually you will only need to use this type of action if an application or installer needs to create a global object, such as a service, or if system changes require unrestricted administrator rights |
| __Remove Administrator Rights__ | This action removes administrative rights for specified applications |
| __Remove Advanced Privileges Action__ | This action removes advanced privileges for specified applications from the process token |

### Allow Copy Action

| Action | Description |
|---|---|
| __Allow Copy to/Applications/Directory__ | This action is used by policies that allow users to run the package installer elevated |

### Application Verifier Action

| Action | Description |
|---|---|
| __Application Compatibility Testing__ | This action triggers application compatibility testing while the process runs and sends the results to the server |

### Apply SVS Layer Action

| Action | Description |
|---|---|
| __Workspace Virtualization Global Layer__ | This action places specified applications in a common Workspace Virtualization global layer |
| __Workspace Virtualization Isolation Layer__ | This action places specified applications in a common Workspace Virtualization isolation layer |

### Advanced Message (Windows)

| Action | Description |
|---|---|
| __Justify Application Elevation Action__ | This action will display a justification prompt to the user before continuing to the process controlled by a policy |
| __Approval Request Form Action__ | This action will display an approval request form for approval before allowing application to run  |
| __Authenticated Justification Message Action__ | This action will display a customized message to the user, allowing for feedback and requiring authentication before running an application |
| __Application Denied Message Action__ | This action will display a modal denial notification message to the user and prevent application execution on Windows  |
| __Application Denied Notification Action__  | This action will display a notification to the user that the process has been denied by a policy. The notification window will fade in and out and automatically close after a period of time |
| __Justify Application Message Action__  | This action will display a justification prompt to the user before continuing to the process controlled by a policy |
| __Group Member Authenticated Message Action__  | This action will display a customized message to the user and requires authentication by a member of the specified group if the end-user is not a member |

### Deny Actions

| Action | Description |
|---|---|
| __Deny Execute__ | This action stops specified applications from executing |
| __Deny Write Access to Executable Files__  | This action can be used to deny write access to common executable files |
| __Deny Read/Write Access to Microsoft Office Document Files__ | This action can be used to deny read and write access to Microsoft Office documents |
| __Deny Windows Hooking__ | This action limits specified applications from interacting in malicious ways with other applications |

### Display Advanced Message Actions

| Action | Description |
|---|---|
| __Application Justification Message Action__ | Application Justification Message Action for Mac OS  |
| __Application Approval Request Message Action__ | Application Approval Request Message Action for Mac OS |
| __Application Warning Message Action__ | Application Warning Message Action for Mac OS |
| __Application Denied Message Action__ | This action will display a modal denial notification message to the user and prevent application execution on MacOS |

### Display User Message - Basic

| Action | Description |
|---|---|
| __Quarantine Message__ | This action displays a message to the user informing them that an application has been quarantined  |
| __Limit Process Rights for New Applications Message__ | This action displays a message to the user informing them that an application has had its rights reduced |
| __SWV Global Layer User Message__  | This action displays a message to the user informing them that an application has been placed in SWV global layer |
| __SWV Isolation Layer User Message__ | This action displays a message to the user informing them that an application has been placed in SWV isolation layer |
| __Deny Execute Message__ | This action displays a message to the user informing them that an application has been denied execution |
| __Deny Files Read and Write Access Message__ | This action displays a message to the user informing them that an application will be restricted from certain file access |
| __Windows Hooking Message__ | This action displays a message to the user informing them that an application will be stopped from interacting with other applications |
| __Remove Rights Message__  | This action displays a message to the user informing them of an associated action |

### Encrypt Application Files

| Action | Description |
|---|---|
| __Encrypt Microsoft Office Documents__ | This action can be used to automagically encrypt common application documents using Windows EFS |

### Execute Application Action

| Action | Description |
|---|---|
| __Immediate File Inventory__ | This action will inventory the file being executed |

### GenericDetourAction

| Action | Description |
|---|---|
| __Enable UAC Virtualization__ | This action will turn on UAC virtualization for the target process |

## Meter Application Action

| Action | Description |
|---|---|
| __Meter Application Usage__ | This action meters the usage of the specified applications |

## Quarantine File Action

| Action | Description |
|---|---|
| __File Quarantine__ | This action can be used to quarantine a file by moving it to the default agent quarantine path |

### Set Environment Variable Action

| Action | Description |
|---|---|
| __Suppress User Account Control Consent Dialog__ | This action will prevent the UAC consent dialog from being displayed |

### Set Process Security Descriptor

| Action | Description |
|---|---|
| __Locked down Service Process Security Descriptor__ | This action applies a restrictive security descriptor disallowing Administrators the right to terminate the process |