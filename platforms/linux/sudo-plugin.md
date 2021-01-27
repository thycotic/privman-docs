[title]: # (Sudo Plugin)
[tags]: # (unix,linux)
[priority]: # (27)
# Unix/Linux Privilege Manager Sudo Plugin

Privilege Manager's Unix/Linux endpoint agent installation also installs a `sudo` plugin.

Going forward, the `sudo` plugin supports a modular framework that allows third-party policy evaluation to govern whether a command is allowed to run. This architecture allows Privilege Manager to extend `sudo` functionality without replacing it.

The plugin allows for commands that are elevated, specifically via policy and filters, to be re-evaluated and modified to utilize `sudo` to perform those commands.

## Sudo Plugin Installation

The agent install also installs the sudo plugin at `/usr/local/libexec/sudo`. The plugin is owned by root and its configuration is located at `/etc/sudo.conf`.
