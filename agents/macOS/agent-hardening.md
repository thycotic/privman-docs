[title]: # (Agent Hardening)
[tags]: # (endpoints)
[priority]: # (3)

# macOS Agent Hardening

It is not currently possible to prevent a local administrator account on macOS from starting and stopping a background service like the Privilege Manager agent. The generally accepted best practice is for the end user to log into a “standard” (non-administrative) account. This should not be a hardship in conjunction with Privilege Manager, once an appropriate but limited set of tools are enabled for the end user.

When the Privilege Manager agent is installed on a Mac endpoint, three processes run in the background. Two of these are macOS launch daemons that run as root, and the third is a macOS launch agent that runs in the current user’s context. These processes are run by the launchd process, which will automatically relaunch them if they are terminated. Moving Privilege Manager to the Trash in an attempt to disable the functionality will not be allowed by the Finder while the processes are still running; bypassing this requires administrative privileges.

>**Note**: The term “launch agent” has a specific meaning in macOS, and is not related to the use of the word “agent” to describe the Privilege Manager endpoint software.

In addition, a sudo plugin is installed that connects the sudo command to the Privilege Manager policy engine. This modifies the default behavior of the sudo command.

## Possible Areas of Concern

* An administrative user could use the launchctl command to disable the Privilege Manager processes (the launch daemons com.thycotic.acsd and Thycotic.Agent.Service and the launch agent Privilege Manager).

  To mitigate, create a blocking policy for `/bin/launchctl`. [This policy](../../computer-groups/macOS/examples/block-agent-removal.md) prevents a privileged user from unloading, removing, and/or stopping either of the above LaunchDaemons and LaunchAgents.
* The application bundle Privilege Manager.app could be deleted from the command line by an administrative user (possibly after first disabling the sudo plugin).
* The sudo plugin could be disabled by an administrative user by removing or renaming the file /etc/sudo.conf — this can be done from the Finder (i.e. even if the normal use of sudo is blocked by policies implemented through the plugin itself, or if the plugin fails to work normally due to other issues with PM).
* On most Unix systems the command su can be used to log into the root account (assuming one knows the root password), which gives complete access to the system. On macOS the root account is disabled by default, but can be enabled by an administrative user; see the Apple support document at https://support.apple.com/en-us/HT204012.

## Locations of Privilege Manager Files

The Privilege Manager agent is implemented by files in the following locations:

* /Applications/Privilege Manager.app

  This application bundle contains the Privilege Manager launch agent and the com.thycotic.acsd launch daemon, which together implement the main functionality of the PM agent.
* /Library/Application Support/Thycotic/Agent

  This folder contains configuration information and other data necessary for the PM agent.
* /Library/LaunchAgents/com.thycotic.acsgui.plist

  This file is used by the macOS launchd system service to start the Privilege Manager launch agent when the user logs in.
* /Library/LaunchDaemons/com.thycotic.agent.plist

  This file is used by the macOS launchd system service to start the Thycotic.Agent.Service launch daemon when the Mac starts up.
* /Library/Extensions

  In macOS Catalina and earlier, Privilege Manager installs a kernel extension named ThycoticACS.kext into this folder in order to detect and potentially block application launches, file creation, etc. In macOS Big Sur and later, this use of kernel extensions is no longer supported by the system, and so ThycoticACS.kext is not installed.
* /Library/SystemExtensions

  In macOS Big Sur and later, the com.thycotic.acsd.systemextension system extension is automatically copied into this folder when Privilege Manager is first installed. It will remain if Privilege Manager.app is deleted, but can be removed by an administrative user with the systemextensionctl command. This is currently only possible if SIP is disabled.
* /usr/local/thycotic/agent

  This folder contains the launch daemon Thycotic.Agent.Service as well as a number of command line utilities to support the Privilege Manager agent.
* /usr/local/libexec/sudo

  This folder contains the sudo plugin thycotic_plugin.so that integrates Privilege Manager with the sudo command.
* /etc/sudo.conf

  This file is added by the Privilege Manager installer to configure the sudo command to use the Thycotic sudo plugin thycotic_plugin.so when it is run from the command line.
