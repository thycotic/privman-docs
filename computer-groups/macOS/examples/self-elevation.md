[title]: # (Self-elevation)
[tags]: # (macOS, standard user, policy)
[priority]: # (7)
# Application Self-elevation

Finder Sync Extensions allow application control on macOS endpoints. Just as on Windows endpoints, users can request application self-elevation via right-click mouse action. The application control is policy based and the macOS system with the endpoint agent must have been online at least once to request its policies from the Privilege Manager server.

## Configuring Application Self-elevation

Your Privilege Manager needs to be configured to allow self-elevation of applications on an endpoint. Follow these server configuration steps:

1. Navigate to your __MacOS Computers__ computer group and select __Agent Configuration__.
1. Under __Self-Elevation__ set the __Allow Self-Elevate__ switch to __Yes__.
1. In the Menu text entry field you may customize the default __Request run as administrator__ text.
   ![__MacOS Agent Configuration__](images/mac/agent_enable_selfeval.png)
1. Click __Save Changes__.

>**Note**:
>When Self-Elevation options are modified in the __MacOS Agent Configuration__, client items on a macOS system must be updated and on older versions of macOS the user must logout and login for the changes to take effect.

After enabling Self-Elevation of applications in the __MacOS Agent Configuration__, you can create policies to target the __User Requested Run As Administrator Filter (macOS)__ and specify which action you want taken. If you choose Approval Request, users will have to request and gain approval before having the application elevated.

## How to Request an Application Run as Administrator

To request to run an application as Administrator, the user at the macOS endpoint navigates to and selects the applications in Finder and uses either right-click or Control+Click to invoke Finder’s context menu:

![Request run as administrator](images/mac/app_run_as_admin_20190506.png "Request run as administrator")

Here the user selects the Request run as administrator menu option.

Depending on the policy in place, this will either be granted immediately or trigger an approval request.

## Troubleshooting: Verify the Finder Extension is Installed

The Finder Privilege Manager extension installs by default during an agent install or upgrade. The extension is enabled/disabled based on the __MacOS Agent Configuration__ policy on the Privilege Manager Server. If the extension is not enabled, check with your system administrator.

1. Open __System Preferences | Extensions__.
1. Select __Finder Extensions__.
1. Verify that Privilege Manager Extension is listed and enabled for customizing Finder.

![Verify extension is listed and enabled](images/mac/app_extension_20190506.png "Verify extension is listed and enabled")

Once the Privilege Manager Extension is enabled, the extension icon is visible in Finder.

![Request run as administrator](images/mac/finder_extension.png "Request run as administrator")

The extension is also present as a menu item when you right-click or control+click an application in Finder.

![Request run as administrator](images/mac/finder_ext_ctrclk.png "Request run as administrator")
