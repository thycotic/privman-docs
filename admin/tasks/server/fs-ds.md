[title]: # (Directory Services)
[tags]: # (foreign systems)
[priority]: # (3)

# Directory Services Tasks

The directory services tasks in this component are all covering different type of directory services imports.

You find the tasks when you:

1. Navigate to __Admin | Tasks__.
1. On the Tasks tab under Jobs and Tasks, select __Server Tasks__.
1. Select __Foreign Systems | Directory Services__.

## Import Azure AD Resources

This task will import devices, users, and groups from Azure AD.

### Parameters

* Directory: The Azure AD instance from which to import/synchronize.
* Import Users: If set, then this task will search for users in the given Azure AD instance.
* Import Groups: If set, then this task will search for groups in the given Azure AD instance.
* Import Devices: If set, then this task will search for devices in the given Azure AD instance.
* Create users when not matched: If set, then users not matched to an existing resource in Privilege Manager will be created.
* Create groups when not matched: If set, then groups not matched to an existing resource in Privilege Manager will be created.
* Create devices when not matched: If set, then devices not matched to an existing resource in Privilege Manager will be created.

  >**Note**: Devices are particularly vulnerable to duplication due to the lack of identifiers in Azure AD. Refer to [Best Practices for AD Imports](../../../how-to/best-practices/ad-import/index.md) for details.

## Import Directory Computers

Run this task to import/update computers and their OUs.

### Parameters

* Directory Id: The directory Id from which to import/synchronize. This is the only required parameter for this task.
* Directory partner Id:
* Full sync:
* Query: Where the object class = the computer.
* Search configuration:

## Import Directory Sites

Run this task to import/update directory sites.

### Parameters

* Directory Id: The directory Id from which to import/synchronize. This is the only required parameter for this task.
* Directory partner Id:
* Full sync:
* Query: Where the object class = the site.
* Search configuration:

## Import Directory Users and Groups

Run this task to import/update users, groups, and their OUs.

### Parameters

* Directory Id: The directory Id from which to import/synchronize. This is the only required parameter for this task.
* Directory partner Id:
* Full sync:
* Query: Where the object class = the site.
* Search configuration:

## Import Directory OU

Run this task to import resources from a specific Directory Services OU.

### Parameters

* Organization Unit:

## Import Specific Azure AD Users and Groups

This task will import the specified users, devices, groups, and optionally child groups, users, and devices from Azure AD.

### Parameters

* Azure AD: The Azure AD instance from which to import/synchronize.
* Create groups when not matched (no): If set, then devices not matched to an existing resource in Privilege Manager will be created.

  >**Note**: Devices are particularly vulnerable to duplication due to the lack of identifiers in Azure AD. Refer to [Best Practices for AD Imports](../../../how-to/best-practices/ad-import/index.md) for details.
* Create groups when not matched (yes): If set, then groups not matched to an existing resource in Privilege Manager will be created.
* Create users when not matched: If set, then users not matched to an existing resource in Privilege Manager will be created.
* Device names: The display names of the devices to import. Leave empty for none. Use a newline between names. End name with '*' to find all that start with the given name.
* Group display names: The display names of the groups to import. Leave empty for none. Use a newline between names. End name with '*' to find all that start with the given name.
* Import child devices: If set, then child devices of any discovered group will be imported.
* Import child users: If set, then child users of any discovered group will be imported.
* Recurse child groups: If set, then child groups of the given group names will be imported recursively.
* User names: The display names or user principal names (UPN) of the users to import. Leave empty for none. Use a newline between names. End name with '*' to find all that start with the given name.
