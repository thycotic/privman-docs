# SecurityManagementService

## Path

/api/securitymanagement

## Description

This service contains methods to get details on the current logged in user, their group membership, and permissions assigned to them.  In addition it allows the getting and setting of access control lists to control security at the item or folder level

## Methods:

* GetCurrentUser – This method returns the contract of the current user
* GetCurrentUserID – This method returns the ID of the current user
* CheckPrivilege – This method checks if the user has a specific privilege
* GetAllPrivileges – This method returns all privileges that the current user has
* GetAllPrivilegeGroups – This method returns all groups that the current user is a member of
* GetItemAccessControlList – This method returns the ACL for an item
* SetItemAccessControlList – This method sets the ACL on an item
* GetEffectivePermissionsForItem – This method gets the effective permissions (including inheritance) for an item