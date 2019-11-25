[title]: # (Unable to Access)
[tags]: # (sign in)
[priority]: # (2)
# Unable to Access Privilege Manager

When attempting to log in to Privilege Manager, you are unable to access the application window and see the following screen.

![Unable to access Privilege Manager](images/unable-to-access-privilege-manager/pm-1.png)

## Resolve

1. Open __Internet Information Services (IIS) Manager__.
1. Expand __Sites__.

   ![Unable to access Privilege Manager](images/unable-to-access-privilege-manager/pm-2.png)
1. Click the __TMS__ Site.

   ![Unable to access Privilege Manager](images/unable-to-access-privilege-manager/pm-3.png)
1. Click on __Authentication__.

   ![Unable to access Privilege Manager](images/unable-to-access-privilege-manager/pm-4.png)
1. Right-click on __Anonymous Authentication__.
1. Click __Enable__.

   ![Unable to access Privilege Manager](images/unable-to-access-privilege-manager/pm-5.png)
1. Right-click on __Windows Authentication__.
1. Click on __Disable__.

   ![Unable to access Privilege Manager](images/unable-to-access-privilege-manager/pm-6.png)
1. Open __Powershell__, type `iisreset` and press __Enter__.

   ![Unable to access Privilege Manager](images/unable-to-access-privilege-manager/pm-7.png)
1. Launch Privilege Manager.
