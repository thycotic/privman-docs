[title]: # (PM Users)
[tags]: # (admin,configuration)
[priority]: # (2)
# Privilege Manager Users

Administrator users can create and edit Privilege Manager users and assign and remove roles for these users.

There are three types of users:

* Thycotic One users - these are only available in cloud environments.
* API Users - these are available for the public API implementation.
* Standard Users - these are users added by an administrator after the initial installation of Privilege Manager.

Standard users can view and edit their own accounts, such as password updates, but can't create new users or delete their own user.

## Creating a New User

1. Navigate to __Admin | User__.

   ![users menu](images/pm-user-1.png "Navigating to the Users menu")
1. Click __New__.

   ![new](images/pm-user-2.png "Selecting New to open the new user modal")

   On-prem instances see a note that Thycotic One users can only be created if a Thycotic One Foreign System is configured.
1. On the __Select a User Type__ modal, from the drop-down select the type of user you want to add.

   ![user type](images/pm-user-3.png "Selecting user type")
1. Click __Create__.

   ![details](images/pm-user-4.png "Enter User details")
1. On the __Enter User Details__ modal, enter

   1. the __User Name__.
   1. the __Display Name__.
1. Click __Create__. The __User Details__ page opens.

   ![full details](images/pm-user-5.png "Enter remaining User details")
1. On the newly created User's details page, add

   * the user's __email address__
   * a __password__.
   * __roles__ to the user by clicking the __Add roles to a user here__ link. You can create users without assigning roles. To go through the steps of assigning roles, refer to the __Add Roles to a User__ topic below.
1. Click __Save Changes__.

The user is now active in the system and you may edit the user details.

![active user](images/pm-user-6.png "Active user details page")

## Add Roles to a User

1. On the __User Details__ page, from the __Add roles to user here__ click __here__.

   ![pm roles](images/roles.png "Add roles to a user")
1. From the roles page select the role you want to add to the user, for example _Privilege Manager Windows Administrators_.

​   ![role edit](images/role-edit.png "Edit link on roles page")
1. Click __Edit__.

​   ![search user](images/assign-user.png "Enter user display name in search")
1. Click the __name__ or __Add__ to add the user to the role.

   ![add user](images/added.png "User added to the role click update")
1. Click __Update__.

   ![save user](images/save.png "Save the changes")
1. Click __Save Changes__ to save the role update.