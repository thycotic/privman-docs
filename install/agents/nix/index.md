[title]: # (Installing Unix/Linux Agents)
[tags]: # (agent,install,upgrade,unix,linux)
[priority]: # (1)

# Installing Unix/Linux Agents

This section provides information that guides you through the Privilege Manager Unix/Linux agent installation steps.

Once you have [downloaded the latest version](../../sw-downloads.md) of the installer you will need to securely copy it onto your host. You will need to perform the installation as root or a user with root sudo permissions.

## Prerequisites

The agent should have a resolvable hostname set. If the agent has a default hostname of `localhost.localdomain`, the pmagent service will not function as expected.

**Note**: Updating the agent hostname post installation will require a reinitialization of the agent configuration.

## Unix/Linux Agent System Requirements

| **Operating System** | **Disk Space Requirements**  | **Minimum Memory** | **Other** |
| ----- | ----- | ----- | ----- |
| CentOS 7.x, 8.x | 100Mb - 2mb in each of /lib64 /etc/pam.d /usr/lib64/security and /etc | 2Gb | For the Identity Bridge component to function correctly **SELinux** currently needs to be [disabled on the host](linux.md#disable_security-enhanced_linux). |
| RedHat Linux 7.x, 8.x |  100Mb - 2mb in each of /lib64 /etc/pam.d /usr/lib64/security and /etc | 2Gb | For the Identity Bridge component to function correctly **SELinux** currently needs to be [disabled on the host](linux.md#disable_security-enhanced_linux). |
| Oracle Linux, 7.x, 8.x | 100Mb - 2mb in each of /lib64 /etc/pam.d /usr/lib64/security and /etc | 2Gb | For the Identity Bridge component to function correctly **SELinux** currently needs to be [disabled on the host](linux.md#disable_security-enhanced_linux). |
| Ubuntu 18.04, 20.04 | 100Mb - 2mb in each of /`lib/x86_64-linux-gnu/security`, `/lib/x86_64-linux-gnu/` `/etc/pam.d` and `/etc` | 2 Gb | |
