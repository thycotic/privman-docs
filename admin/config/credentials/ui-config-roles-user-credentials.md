[title]: # (User Credentials)
[tags]: # (establish)
[priority]: # (2)
# User Credentials and Roles

As described for the Roles Tab, Privilege Manager comes with a set of default user roles. Those roles can be edited or new ones can be added to the system.

The role for the Privilege Manager Administrator gives permissions to manage all aspects of the Privilege Manager implementation. As a best practice, it is recommended to set-up roles that limit administrative access to tasks directly related with a users job role.

For integrations with Secret Server keep in mind that Privilege Manger has the ability to use Secret Server as its storage container for credentials. This includes credentials for connecting to integrated systems such as Service Now, as well as credentials for local accounts that are managed by Local Security in Privilege Manager. Customers can choose to integrate with Secret Server only (no Vault setup) or Secret Server and Vault. Either option requires Authentication Data setup for Foreign Systems in Privilege Manager. Refer to the [Setting up Integration between Privilege Manager and Secret Server](../../foreign-sys/thycotic/set-up-pm-ss-integration.md) topic.

If you are integrating with Active Directory synchronization please refer to [Active Directory Synchronization](../../../local-security/ad-sync.md).

>**Note**:
>If you synced with Azure AD, and then added that user to the Privilege Manager Administrators Role, that Azure AD user has admin rights only, if Azure AD is used as the auth provider. If users login via Thycotic One, use __Admin | Users__ to create a new user and then add that new user to the Privilege Manager Administrators Role, refer to [How to Add Thycotic One Users Manually](../../users/index.md).

## Create User during Installation

During the installation process the Create User page is where you enter information for the initial Privilege Manager Administrator user. Please remember these credentials as they are necessary to login to the web application after you complete the installation.
