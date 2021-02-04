[title]: # (Installing Unix/Linux Agents)
[tags]: # (agent,install,upgrade,unix,linux)
[priority]: # (1)

# Installing Unix/Linux Agents

This section provides information that guides you through the Privilege Manager Unix/Linux agent installation steps.

Once you have [downloaded the latest version](../../sw-downloads.md) of the installer you will need to securely copy it onto you host. You will need to perform the installation as root or a user with root sudo permissions.

## Prerequisites

The agent should have a resolvable hostname set. If the agent has a default hostname of `localhost.localdomain`, the pmagent service will not function as expected.

**Note**: Updating the agent hostname post installation will require a reinitialization of the agent configuration.

## Unix/Linux Agent System Requirements

| **Operating System** | **Disk Space Requirements**  | **Minimum Memory** | **Other** |
| ----- | ----- | ----- | ----- |
| CentOS 7.x, 8.x | 100Mb - 2mb in each of /lib64 /etc/pam.d /usr/lib64/security and /etc | 2Gb | For the Identity Bridge component to function correctly **SELinux** currently needs to be [disabled on the host](inst-agent/index.md#disable_security-enhanced_linux). |
| RedHat Linux 7.x, 8.x |  100Mb - 2mb in each of /lib64 /etc/pam.d /usr/lib64/security and /etc | 2Gb | For the Identity Bridge component to function correctly **SELinux** currently needs to be [disabled on the host](inst-agent/index.md#disable_security-enhanced_linux). |
| Oracle Linux, 7.x, 8.x | 100Mb - 2mb in each of /lib64 /etc/pam.d /usr/lib64/security and /etc | 2Gb | For the Identity Bridge component to function correctly **SELinux** currently needs to be [disabled on the host](inst-agent/index.md#disable_security-enhanced_linux). |
| Ubuntu 18.04, 20.04 | 100Mb - 2mb in each of /`lib/x86_64-linux-gnu/security`, `/lib/x86_64-linux-gnu/` `/etc/pam.d` and `/etc` | 2 Gb | |

### Windows & Active Directory Requirements

* Active Directory Forest Functional Level: Greater than or equal to 2012 R2 or newer
* Windows OS: Greater than or equal to Windows 2012 R2/Windows 7 (x64 only across all versions of Windows)
* Client Prerequisites:
  * Visual Studio C++ Redistributable 2019 x64 (https://aka.ms/vs/16/release/vc_redist.x64.exe)
  * Visual Studio C++ Redistributable 2019 x86 (https://aka.ms/vs/16/release/vc_redist.x86.exe)
  * ASP.NET Core 3.1 Runtime (v3.1.5) - Windows Hosting Bundle (https://download.visualstudio.microsoft.com/download/pr/7c30d3a1-f519-4167-b850-b9c49bf2aa0e/dbfa957a76a41a1e1795f59d400d4ccd/dotnet-hosting-3.1.5-win.exe)
  * .NET 4.5.2 (https://download.microsoft.com/download/E/2/1/E21644B5-2DF2-47C2-91BD-63C560427900/NDP452-KB2901907-x86-x64-AllOS-ENU.exe)
