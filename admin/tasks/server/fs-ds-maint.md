[title]: # (Directory Services Maintenance)
[tags]: # (foreign systems)
[priority]: # (3)

# Directory Services Maintenance Tasks

The tasks in this component all help with the maintenance of directory services resources. These tasks are read-only items that need to be duplicated for any task customization.

You find the tasks when you:

1. Navigate to __Admin | Tasks__.
1. On the Tasks tab under Jobs and Tasks, select __Server Tasks__.
1. Select __Foreign Systems | Directory Services__.
1. Select __Maintenance__.

## Delete Imported Azure AD Resources

This task will delete users, groups, and devices from Privilege Manager that were imported from Azure AD.

### Parameters

* Directory: The Azure AD instance from which to delete resources.
* Delete users: If set, then this task will delete users from Privilege Manager imported from the given directory.
* Delete groups: If set, then this task will delete groups from Privilege Manager imported from the given directory.
* Delete devices: If set, then this task will delete computers and other devices from Privilege Manager imported from the given directory.
* Ignore dependencies: Use this as a last resort if you wish to delete and ignore any items that depend on the resources being deleted.

## Delete Imported Directory Resources

This task will delete users, groups, computers, OUs, and Sites from Privilege Manager that were imported from AD.

### Parameters

* Directory: The AD instance from which to delete resources.
* Delete users: If set, then this task will delete users from Privilege Manager imported from the given directory.
* Delete groups: If set, then this task will delete groups from Privilege Manager imported from the given directory.
* Delete computers: If set, then this task will delete computers from Privilege Manager imported from the given directory.
* Delete organization: If set, then this task will delete OUs from Privilege Manager imported from the given directory.
* Delete sites: If set, then this task will delete sites from Privilege Manager imported from the given directory.
* Ignore dependencies: Use this as a last resort if you wish to delete and ignore any items that depend on the resources being deleted.

## Merge Computers with Duplicate Azure Device IDs

This task will merge computers with duplicate Azure AD Device IDs.

### Parameters

* Directory: The Azure AD instance from which to merge resources. Leave empty for all.

## Merge Duplicate Account SID Resources

Run this task to merge resources that have a duplicate account SID.

### Parameters

* Target Resources: Leave empty to automatically discover all. Select only the target, not its duplicates. Any resources with SID matching a target will be merged into the target.

## OU Directory Scope Collection Update

This task updates the membership of Directory Services OU scope collections based on a selected Schedule Type.

## Update OU Directory Scope Collections Membership

This task updates the membership of Directory Services OU scope collections.

### Parameters

* Directory collections: The set of directory collections whose membership will be updated.

## Update OU Directory Scope Collections Membership 2

This task updates the membership of Directory Services OU scope collections. 

### Parameters

This task has a __Force all__ parameter that forces the membership of all directory scope collections to update, regardless of an update required detection.
