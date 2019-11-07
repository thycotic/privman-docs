[title]: # (Using the Remove Program Utility)
[tags]: # (create,set-up)
[priority]: # (2)
# Using the Remove Programs Utility

The Remove Programs Utility provides a solution to the following problem:

Windows standard users are not able to remove applications from the control panel because of Windows checking for admin rights. This utility is available for deployment via Privilege Manager.

Customers can use this utility in any of the following ways:

* Allow users to uninstall any and all applications by using the utility.
* Make the utility show an approval request for each uninstaller that is launched.
* Make the utility show an approval prompt when it launches.

The utility will list all the same applications as the Remove Programs in the Control Panel, but it can also hide software that end users should not be able to uninstall (such as the Thycotic agents).

With Privilege Manager version 10.7 Thycotic is introducing support for Windows 10 __Apps & Features__ and the management of Windows Store apps via the __Remove Programs Helper__. Certain apps designed as a Windows 10 package are registered in __Apps & Features__ but do not appear in the operating systems Add Remove Programs options. Privilege Manager locates those applications and provides management via the enhanced __Remove Programs Utility__.

The steps to deploy and use the utility are detailed below.

## Download and Install Config Feed

1. Navigate to Admin | More | Config Feeds
1. In the row for "Privilege Manager Product Configuration Feeds", click __Select Items__.

   ![Data Feeds](images/remove-pro/rpu-1.png)
1. In the row for "Application Control Solution", click __Select Items__.

   ![ACS select](images/remove-pro/rpu-2.png)
1. In the row for "Application Control – Remove Programs Helper", click on __Download__. This downloads and installs the deployment policy and an elevation policy to the server. The elevation policy is included in the Config Feed because the utility needs to run elevated.

   ![ACS Download](images/remove-pro/rpu-3.png)
1. After the download/installation is complete a "Installed" indicator shows.

   ![ACS Installed](images/remove-pro/rpu-4.png)

## Add and Customize the Policy

After the config feed has been downloaded and installed, add and customize the policy.

1. Navigate to __Admin | Policies__, which defaults to the General tab.

   ![List of Policies on the General tab](images/remove-pro/rpu-5.png)
1. Click on the row listing the __Add Thycotic Remove Programs__ policy.

   ![Parameters view](images/remove-pro/rpu-6.png)
1. On the Parameters tab customize the function of the utility. Several parameters and attributes are available for customization in the various tabs on the page. Click __Edit__ to customize.
1. __Enable__ the policy.
1. Click __Save__ to save all changes you made.

### Customization Options

Listed below are some of the customization options available:

* Choose whether a shortcut on the start menu or on the control panel should be created.
* List products that you want to prevent being uninstalled. There are two options for this:
  * If the "Show Blocked Installers in List" option is unchecked, the products will be hidden.
  * If the "Show Blocked Installers in List" option is checked, the products will just be disabled from being uninstalled.
* Specify the computers to be targeted.
* Set the trigger, which determines how often you want the policy from the Task Scheduler on the endpoint to check to ensure the settings match.

If you selected "Create Start Menu Shortcut", the users will see Thycotic Remove Programs on the Start Menu.

If you selected "Add to Control Panel", the users will see an addition on the Control Panel such as shown below:

![Control Panel icon](images/remove-pro/rpu-7.png)

## Use the Utility

The utility is straightforward to use: users can select the row containing the program that they want to uninstall and then select the uninstall button.

![Utility in use](images/remove-pro/rpu-8.png)
