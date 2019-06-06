[title]: # (List of Actions)
[tags]: # (overview,out-of-box)
[priority]: # (5000)
# List of Actions

Described here are the out-of-the-box actions that are available in Privilege Manager and can be used to make your policy configuration process easy. 
When creating new actions in Privilege Manager, these are the list of category
options you may use:

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
| **Run as Root** | Adjust the process rights of the application to run as the root user (MacOS) |

### Adjust Process Rights Action

| Action | Description |
|---|---|
| **Add Administrative Rights** | This action adds basic administrative rights needed to install and run specified applications |
| **Add Administrator Rights – Unrestricted** | This action adds administrative rights at a higher integrity level for specified applications. Usually you will only need to use this type of action if an application or installer needs to create a global object, such as a service, or if system changes require unrestricted administrator rights |
| **Remove Administrator Rights** | This action removes administrative rights for specified applications |
| **Remove Advanced Privileges Action** | This action removes advanced privileges for specified applications from the process token |

### Allow Copy Action

| Action | Description |
|---|---|
| **Allow Copy to/Applications/Directory** | This action is used by policies that allow users to run the package installer elevated |

### Application Verifier Action

| Action | Description |
|---|---|
| **Application Compatibility Testing** | This action triggers application compatibility testing while the process runs and sends the results to the server |

### Apply SVS Layer Action

| Action | Description |
|---|---|
| **Workspace Virtualization Global Layer** | This action places specified applications in a common Workspace Virtualization global layer |
| **Workspace Virtualization Isolation Layer** | This action places specified applications in a common Workspace Virtualization isolation layer |

### Advanced Message (Windows)

| Action | Description |
|---|---|
| **Justify Application Elevation Action** | This action will display a justification prompt to the user before continuing to the process controlled by a policy |
| **Approval Request Form Action** | This action will display an approval request form for approval before allowing application to run  |
| **Authenticated Justification Message Action** | This action will display a customized message to the user, allowing for feedback and requiring authentication before running an application |
| **Application Denied Message Action** | This action will display a modal denial notification message to the user and prevent application execution on Windows  |
| **Application Denied Notification Action**  | This action will display a notification to the user that the process has been denied by a policy. The notification window will fade in and out and automatically close after a period of time |
| **Justify Application Message Action**  | This action will display a justification prompt to the user before continuing to the process controlled by a policy |
| **Group Member Authenticated Message Action**  | This action will display a customized message to the user and requires authentication by a member of the specified group if the end-user is not a member |

### Deny Actions

| Action | Description |
|---|---|
| **Deny Execute** | This action stops specified applications from executing |
| **Deny Write Access to Executable Files**  | This action can be used to deny write access to common executable files |
| **Deny Read/Write Access to Microsoft Office Document Files** | This action can be used to deny read and write access to Microsoft Office documents |
| **Deny Windows Hooking** | This action limits specified applications from interacting in malicious ways with other applications |

### Display Advanced Message Actions

| Action | Description |
|---|---|
| **Application Justification Message Action** | Application Justification Message Action for Mac OS  |
| **Application Approval Request Message Action** | Application Approval Request Message Action for Mac OS |
| **Application Warning Message Action** | Application Warning Message Action for Mac OS |
| **Application Denied Message Action** | This action will display a modal denial notification message to the user and prevent application execution on MacOS |

### Display User Message - Basic

| Action | Description |
|---|---|
| **Quarantine Message** | This action displays a message to the user informing them that an application has been quarantined  |
| **Limit Process Rights for New Applications Message** | This action displays a message to the user informing them that an application has had its rights reduced |
| **SWV Global Layer User Message**  | This action displays a message to the user informing them that an application has been placed in SWV global layer |
| **SWV Isolation Layer User Message** | This action displays a message to the user informing them that an application has been placed in SWV isolation layer |
| **Deny Execute Message** | This action displays a message to the user informing them that an application has been denied execution |
| **Deny Files Read and Write Access Message** | This action displays a message to the user informing them that an application will be restricted from certain file access |
| **Windows Hooking Message** | This action displays a message to the user informing them that an application will be stopped from interacting with other applications |
| **Remove Rights Message**  | This action displays a message to the user informing them of an associated action |

### Encrypt Application Files

| Action | Description |
|---|---|
| **Encrypt Microsoft Office Documents** | This action can be used to automagically encrypt common application documents using Windows EFS |

### Execute Application Action

| Action | Description |
|---|---|
| **Immediate File Inventory** | This action will inventory the file being executed |

### GenericDetourAction

| Action | Description |
|---|---|
| **Enable UAC Virtualization** | This action will turn on UAC virtualization for the target process |

## Meter Application Action

| Action | Description |
|---|---|
| **Meter Application Usage** | This action meters the usage of the specified applications |

## Quarantine File Action

| Action | Description |
|---|---|
| **File Quarantine** | This action can be used to quarantine a file by moving it to the default agent quarantine path |

### Set Environment Variable Action

| Action | Description |
|---|---|
| **Suppress User Account Control Consent Dialog** | This action will prevent the UAC consent dialog from being displayed |

### Set Process Security Descriptor

| Action | Description |
|---|---|
| **Locked down Service Process Security Descriptor** | This action applies a restrictive security descriptor disallowing Administrators the right to terminate the process |