[title]: # (CentOS/RedHat/Oracle Linux)
[tags]: # (agent,install,upgrade,unix,linux)
[priority]: # (2)

# Installing on CentOS/RedHat/Oracle Linux

There are 2 methods for installing packages, __rpm__ and __yum__, both methods are outlined below.

## Thycotic File Locations

Core installation location: `/opt/thycotic`

Other Thycotic file locations: `/lib64`, `/usr/lib64/security`, `/var/log`, `/etc`

Other locations Thycotic agent will modify system files: `/etc`, `/etc/pam.d`, `/etc/ssh`, `/etc/authselect/`

## Disable Security-Enhanced Linux (SELinux)

Currently for the Thycotic Identity Bridge agent to correctly authenticate against Active Directory, Thycotic requires that the SELinux functionality of the host machine be disabled.

The agent installer will detect if SELinux is set to Enforcing or Permissive and provide the following message at the end of the installation.

```
========================================================================
Please disable SELinux to allow the Identity Bridge to function properly
========================================================================
```

To disable the SELinux functionality you will need to perform the following:

1. Edit the /etc/selinux/config file
1. Set the SELINUX line to: disabled
   * Example: SELINUX=disabled
1. Reboot your host

If SELinux is disabled the message will not be displayed.

For CentOS, RedHat, and Oracle there are 2 methods for installing packages, rpm and yum, both methods are outlined below.

## RPM

Performed as non root user with sudo permissions:

`>> sudo rpm -i /root/Thycotic/pmagent_x86_64_vn.n.n.nn.rpm`

Where, pmagent_x86_64_vn.n.n.nn.rpm is replaced with the actual software package and version that is being installed.

Below is the expected output of a successful installation

```
Created symlink from /etc/systemd/system/multi-user.target.wants/pmagent.service to /etc/systemd/system/pmagent.service.

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

## YUM

Performed as non root user with sudo permissions:

`>> sudo yum install /root/Thycotic/pmagent_x86_64_vn.n.n.nn.rpm`

Where, pmagent_x86_64_vn.n.n.rpm is replaced with the actual software package and version that is being installed.

Below is the expected output of a successful installation

```
Loaded plugins: fastestmirror, langpacks
Examining ./pmagent_x86_64_v1.1.3.79_centos7.rpm: pmagent-1.1.3.79-1.x86_64
Marking ./pmagent_x86_64_v1.1.3.79_centos7.rpm to be installed
Resolving Dependencies
--> Running transaction check
---> Package pmagent.x86_64 0:1.1.3.79-1 will be installed
--> Finished Dependency Resolution
base/7/x86_64                           | 3.6 kB  00:00:00
epel/x86_64/metalink                    |  19 kB  00:00:00
epel/x86_64                             | 4.7 kB  00:00:00
epel/x86_64/updateinfo                  | 1.0 MB  00:00:00
epel/x86_64/primary_db                  | 6.9 MB  00:00:01
extras/7/x86_64                         | 2.9 kB  00:00:00
updates/7/x86_64                        | 2.9 kB  00:00:00
updates/7/x86_64/primary_db             | 4.7 MB  00:00:01

Dependencies Resolved

==============================================================================================
 Package            Arch          Version         Repository                            Size
==============================================================================================
Installing:
 pmagent            x86_64        1.1.3.79-1        /pmagent_x86_64_v1.1.3.79_centos7       22 M

Transaction Summary
==============================================================================================
Install  1 Package

Total size: 22 M
Installed size: 22 M
Is this ok [y/d/N]: y
Downloading packages:
Running transaction check
Running transaction test
Transaction test succeeded
Running transaction
Warning: RPMDB altered outside of yum.
  Installing : pmagent-1.1.3.79-1.x86_64                                                 1/1
Created symlink from /etc/systemd/system/multi-user.target.wants/pmagent.service to /etc/systemd/system/pmagent.service.

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

  Verifying  : pmagent-1.1.3.79-1.x86_64                                               1/1

Installed:
  pmagent.x86_64 0:1.1.3.79-1

Complete!
```

## Post Installation

By default CentOS, RedHat, and Oracle do not start a newly installed package, therefore you will need to manually start the Thycotic Agent.

Performed as non root user with sudo permissions:

`>> sudo systemctl start pmagent.service`

The pmagent service will be started automatically following a reboot of the host system.
