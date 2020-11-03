[title]: # (Sudo Plugin)
[tags]: # (macOS)
[priority]: # (27)
# macOS Sudo Plugin

Thycotic supports command line filtering in order to block, elevate, restrict, or allow commands.

Apple’s Endpoint Security framework is a great leap forward for developers, but it prevents Privilege Manager from performing process elevation of command-line binaries like done in the past. To support the TCC changes in macOS endpoints, the KEXT support is being replaced with a sudo plugin.

Going forward sudo supports a modular framework that allows third-party policy evaluation to govern whether a command is allowed to run. This architecture allows Privilege Manager to extend sudo functionality without replacing it and without introducing too much change to established workflows. For existing customers, if privileged commands are already running via sudo and a Privilege Manager policy to elevate it, then there is nothing that needs to be changed. However, if some commands are elevated, specifically via policy and filters, those need to be re-evaluated and modified to utilize sudo to perform those commands.

## Command Syntax

Example: `sudo diskutil -l`
