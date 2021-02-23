[title]: # (Ubuntu)
[tags]: # (agent,install,upgrade,unix,linux)
[priority]: # (2)

# Installing on Ubuntu

There are 2 methods for installing packages, DPKG and APT, both methods are outlined below.

## Prerequisites

If the Ubuntu operating system is installed from either

* ubuntu-18.04-live-server-amd64.iso or
* ubuntu-20.04.1-live-server-amd64.iso

you will be required to update the operating system base files with the following command.

`sudo apt-get update`

It is recommended that your base operating system is always running the latest vendor recommended patches.

## Thycotic File Locations

Core installation location: `/opt/thycotic`

Other Thycotic file locations: `/lib/x86_64-linux-gnu/security`, `/lib/x86_64-linux-gnu/`, `/var/log`, `/etc`

Other locations Thycotic agent will modify system files: `/etc`, `/etc/pam.d`, `/etc/ssh`

## DPKG

Performed as non root user with sudo permissions

`>> sudo dpkg -i pmagent_x86_64_vn.n.n.nn_ubuntuXX.deb`

Below is the expected output of a successful installation

```
Selecting previously unselected package pmagent.
(Reading database ... 344578 files and directories currently installed.)
Preparing to unpack pmagent_x86_64_v1.1.3.79_ubuntu18.deb ...
Unpacking pmagent (1.1.3.79) ...
Setting up pmagent (1.1.3.79) ...
Created symlink /etc/systemd/system/multi-user.target.wants/pmagent.service → /etc/systemd/system/pmagent.service.

Please start the pmagent service by running:
    /bin/systemctl start pmagent.service

This installation can be used as an agent for the Thycotic Privilege Manager
and/or an agent for the Thycotic Identity Bridge.

If you are using this installation as a Thycotic Privilege Manager agent,
You must now register this agent with the Thycotic Privilege Manager
using the command:
    /opt/thycotic/sbin/pmagent --register <host:port> <install code>

If you are using this installation as a Thycotic Identity Bridge agent,
You need to join an Active Directory domain to start authenticating users
using the command:
    /opt/thycotic/sbin/pmagent --join
```

## APT

Performed as non root user with sudo permissions

`>> sudo apt install /root/Thycotic/pmagent_x86_64_vn.n.n.nn_ubuntuXX.deb`

Below is the expected output of a successful installation

```
Reading package lists... Done
Building dependency tree
Reading state information... Done
Note, selecting 'pmagent' instead of './pmagent_x86_64_v1.1.3.79_ubuntu18.deb'
The following packages were automatically installed and are no longer required:
  efibootmgr libfwup1 libllvm9 linux-hwe-5.4-headers-5.4.0-42 linux-hwe-5.4-headers-5.4.0-47 linux-hwe-5.4-headers-5.4.0-48 linux-hwe-5.4-headers-5.4.0-51 linux-hwe-5.4-headers-5.4.0-52
  linux-hwe-5.4-headers-5.4.0-53 linux-hwe-5.4-headers-5.4.0-56 linux-hwe-5.4-headers-5.4.0-58 linux-hwe-5.4-headers-5.4.0-59 linux-hwe-5.4-headers-5.4.0-60 tcpd
Use 'apt autoremove' to remove them.
The following NEW packages will be installed
  pmagent
0 to upgrade, 1 to newly install, 0 to remove and 6 not to upgrade.
Need to get 0 B/10.8 MB of archives.
After this operation, 34.3 MB of additional disk space will be used.
Get:1 /root/Thycotic/pmagent_x86_64_v1.1.3.79_ubuntu18.deb pmagent amd64 1.1.3.79 [10.8 MB]
Selecting previously unselected package pmagent.
(Reading database ... 344578 files and directories currently installed.)
Preparing to unpack .../pmagent_x86_64_v1.1.3.79_ubuntu18.deb ...
Unpacking pmagent (1.1.3.79) ...
Setting up pmagent (1.1.3.79) ...
Created symlink /etc/systemd/system/multi-user.target.wants/pmagent.service → /etc/systemd/system/pmagent.service.

Please start the pmagent service by running:
    /bin/systemctl start pmagent.service

This installation can be used as an agent for the Thycotic Privilege Manager
and/or an agent for the Thycotic Identity Bridge.

If you are using this installation as a Thycotic Privilege Manager agent,
You must now register this agent with the Thycotic Privilege Manager
using the command:
    /opt/thycotic/sbin/pmagent --register <host:port> <install code>

If you are using this installation as a Thycotic Identity Bridge agent,
You need to join an Active Directory domain to start authenticating users
using the command:
    /opt/thycotic/sbin/pmagent --join
```

## Post Installation

By default Ubuntu does not start a newly installed package, therefore you will need to manually start the Thycotic Agent.

Performed as non root user with sudo permissions:

`>> sudo systemctl start pmagent.service`

The pmagent service will be started automatically following a reboot of the host system.