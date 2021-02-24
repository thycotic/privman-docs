[title]: # (Registration/Status)
[tags]: # (endpoints)
[priority]: # (4)

# Agent Registration and Status

To view agent registration and status information, navigate to __Admin | Agents__.

![registration and status](../images/agents-overview.png "Agents overview page")

The __Summary__ tab provides gauges for

* Managed Operating Systems
* Agent Registration State
* Agent Policy State
* Password Age

Clicking the gauges opens drilldown reports.

The table grid list all endpoint operating systems and the number of endpoints with that operating system. Selecting Unix/Linux shows the list of all agents registered with Privilege Manager, providing the

* Computer Name
* Operating System
* OS Name
* Version
* System Type

![registration and status](images/reg-nix-agents.png "Agents registration and status page")

Clicking on a computer in the list, opens the resource page.

![agent resource](images/nix-agent-resource.png "Agent resource page")

## Registering the Agent

The pmagent service isn’t required to be running for Privilege Manager policies to be executed, although for scheduled jobs to run successfully, the pmagent service need to be registered, for example:

`pmagent --register -u https://192.168.248.201:443 -c WC5W-W2DD-ONLE`

Where:

* -u xxxxxx is the PMServer address and port
* -c xxxxxx is the agent code

You can append command with a -V for extended output.

Once registered the following is inserted into the `/etc/sudo.conf`:

```bash
Plugin sudoers_policy /opt/thycotic/lib64/pmsudo_plugin.so
Path noexec /opt/thycotic/lib64/pmsudo_noexec.so
```

Once registered the following is inserted into the `/etc/shells`:

```bash
/usr/bin/pmsh
```

The Agent will also create a `xxxxxx.thyorig` and `xxxxxx.thybak` files of the original files modified.

* `thyorig` is a copy of the original file before we make any changes.
* `thybak` is a copy of the file taken before any additional changes made. This is being updated during agent upgrades.
