[title]: # (Sudo Plugin)
[tags]: # (macOS)
[priority]: # (27)
# macOS Privilege Manager Sudo Plugin

Apple’s Endpoint Security framework prevents Privilege Manager from performing process elevation of command-line binaries like done in the past. Privilege Manager's previous KEXT support for command line filtering in order to block, elevate, restrict, or allow commands is being replaced with a `sudo` plugin for Apple's newer OS versions starting with Catalina and newer.

Going forward, the `sudo` plugin supports a modular framework that allows third-party policy evaluation to govern whether a command is allowed to run. This architecture allows Privilege Manager to extend `sudo` functionality without replacing it and without introducing too much change to established workflows.

For __existing customers__, if privileged commands are already running via `sudo` and a Privilege Manager policy to elevate it, then there is nothing that needs to be changed. However, if some commands are elevated, specifically via policy and filters, those need to be re-evaluated and modified to utilize `sudo` to perform those commands.

Refer to the [macOS Application Approval Process via Sudo Plugin](../../computer-groups/macOS/examples/approval-sudo.md) topic. This topic explains the workflow for an approval policy elevating applications executed from a specific folder location.

## Sudo Plugin Installation

In support of Big Sur and system extensions, the macOS agent install also installs the macOS sudo plugin at `/usr/local/libexec/sudo`. The plugin is owned by root and its configuration is located at `/etc/sudo.conf`.
