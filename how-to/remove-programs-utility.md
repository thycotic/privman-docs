[title]: # (Using the Remove Program Utility)
[tags]: # (create,set-up)
[priority]: # (9500)
# Using the Remove Programs Utility

URL:
<https://thycotic.force.com/support/s/article/Privilege-Manager-Remove-Programs-Utility>

Summary
=======

This article presents the Thycotic solution to the following problem: Windows
standard users are not able to remove applications from the control panel
because of Windows checking for admin rights. Thycotic provides a utility,
implemented via Privilege Manager, that facilitates the uninstallation of
installed applications, allowing parameters for this privilege to be set by the
customer.

Article
=======

X

The Remove Programs Utility provides a solution to the following problem:
Windows standard users are not able to remove applications from the control
panel because of Windows checking for admin rights. This utility is available
for deployment via Privilege Manager.

Customers could choose to use this utility in any of the following ways:

-   Allow users to uninstall any and all applications by using the utility.

-   Make the utility show an approval request for each uninstaller that is
    launched.

-   Make the utility show an approval prompt when it launches.

The utility will list all the same applications as the Remove Programs in the
Control Panel, but it can also hide software that end users should not be able
to uninstall (such as the Thycotic agents).

The steps to deploy and use the utility are presented in the sections below.

Download and Install Config Feed
================================

Navigate to:

Admin \> More \> Config Feeds

xxx

[pic \# 1] – data feeds

xxx

In the row for “Privilege Manager Product Configuration Feeds”, click on “Select
Items”.

xxx

[pic \# 2] – config feeds

xxx

In the row for “Application Control Solution”, click on “Select Items”.

xxx

[pic \# 3] – ACS - download

xxx

In the row for “Application Control – Remove Programs Helper”, click on
“Download”. This will download and install the deployment policy and an
elevation policy to the server. (An elevation policy is included in the Config
Feed because the utility needs to run elevated.) You will see an “Installed”
indicator in place of the “Download” button.

xxx

[pic \# 4] – ACS - installed

xxx

Add and Customize the Policy
============================

After the config feed has been downloaded and installed, navigate to:

Admin \> Policies \> General

xxx

[pic \# 5] – Policies

xxx

Click on the row listing the “Add Thycotic Remove Programs” policy.

xxx

[pic \# 6] – Parameters-1

xxx

Here you can customize the function of the utility. Several parameters and
attributes are available for customization in the various tabs on the page; some
can be seen in the screenshot above. Click the Edit button to do customization.

xxx

[pic \# 7] – Parameters-2

xxx

Listed below are some of the customizations you can do:

-   Choose whether a shortcut on the start menu or on control panel should be
    created.

-   List products that you want to prevent being uninstalled. There are two
    options for this:

    -   If the “Show Blocked Installers in List” option is unchecked, the
        products will be hidden.

    -   If the “Show Blocked Installers in List” option is checked, the products
        will just be disabled from being uninstalled.

-   Specify the computers to be targeted.

-   Set the trigger (which determines how often you want the policy from the
    Task Scheduler on the endpoint to check to ensure the settings match).

Finally, do not forget to Enable the policy and click Save:

xxx

[pic \# 8] – enabled

xxx

If you selected “Create Start Menu Shortcut”, the users will see an addition on
the Start Menu such as shown below:

xxx

[pic \# 9] – start menu

xxx

If you selected “Add to Control Panel”, the users will see an addition on the
Control Panel such as shown below:

xxx

[pic \# 10] – control panel

xxx

Use the Utility
===============

The utility is straightforward to use: users can select the row containing the
program that they want to uninstall and then select the uninstall button.

xxx

[pic \# 11] – utility

xxx

xxx
