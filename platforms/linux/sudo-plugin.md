[title]: # (Sudo Plugin)
[tags]: # (unix,linux)
[priority]: # (27)
# Unix/Linux Privilege Manager Sudo Plugin

Privilege Manager's Unix/Linux endpoint agent installation also installs a `sudo` plugin.

When the agent performs the registration process the Thycotic sudo plugin is inserted into the sudo configuration and the sudoers file will stop being processed on the agent. Meaning only Privilege Manager Policies are allowed to be processed. By default all sudo commands will now be blocked unless a Privilege Manager policy allows it's execution.

## Sudo Plugin Installation

The agent install also installs the sudo plugin at `/opt/thycotic/lib64`. The plugin is owned by root and its configuration is located at `/etc/sudo.conf`.
