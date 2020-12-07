[title]: # (macOS - Unresponsive Endpoint)
[tags]: # (system recovery)
[priority]: # (10)
# How to Recover an Unresponsive macOS Endpoint

In case a macOS endpoint ever becomes unresponsive due to conflicting policy configurations, the following steps allow a user to recover the endpoint without having to restore or rebuild the system.

>**Note**: Applies to all macOS versions on which the KEXT is supported.

1. Turn off the macOS system.
1. Hold down the ⌘+s keys and power the system back on. Keep holding those keys down until it shows that it is booting in single-user mode.
1. Follow the prompts to mount the root device as read-write. It will instruct you to enter the following:

   ```shell
   /sbin/fsck -fy
   /sbin/mount -uw /
   ```
1. Rename the kernel extension so that you can get back to a functioning macOS:

   ```shell
   cd /Library/Extensions
   mv ThycoticACS.kext ThycoticACS.kext.org
   exit
   ```
1. The system will restart.
1. Disable and/or delete policies that are causing the issue.
1. Update client items before renaming the kernel extension and having it start automatically. You can force client item updates by performing the following in Terminal.app:

   ```shell
   sudo /usr/local/thycotic/agent/updateClientItems.sh
   ```
1. Restore the kernel extension in Terminal.app:

   ```shell
   cd /Library/Extensions
   sudo mv ThycoticACS.kext.org ThycoticACS.kext
   exit
   ```
