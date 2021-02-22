[title]: # (Local File Inventory)
[tags]: # (endpoints)
[priority]: # (4)

# Local Agent File Inventory

The Agent keeps a local cache of files that are run though sudo. It keeps a hash of the file and will only run that file if the hash is correct. When a file hash changes, either by being added for the first time, or by updating using the `--addfiletocache`, a scheduled task will send this information to the Privilege Manager Server, and will appear in the agent's file inventory.

## Sudo Default

The `/usr/bin/sudo` command will always be added to the local inventory, this cannot be deleted.

## Adding to Inventory

### Automatically (sudo/pmsh)

Any commands run via an accepting policy will add the file to the local file catalog, these are then synced to the server's file inventory, an Allow or Elevate policy needs to be in place.

#### pmsh

`pmsh` is an open source shell extension to the Privilege Manager agent functionality.

When the `pmsh` is invoked all commands apart from the built-in shell commands are passed via Privilege Manager's policies stored on the local agent.

When the end user shell has been defined as `pmsh`, there is no need to prefix every command with `sudo`. This allows for seamless control/monitoring over all end user commands.

Example use case for implementing `pmsh`:

By creating a pass through Allow policy of all commands, a user is able to continue working on the agent as they normally are; However, the agent is adding commands to the file inventory and uploading those to the Privilege Manager server for auditing and built-out of a common list of commands executed.

Additional policies can be defined to Block or Elevate commands deemed appropriate by the administrators.

When the agent is registered with a Privilege Manager server, a `/usr/bin/pmsh` entry is added to the `/etc/shells` file

>**Note**: `pmsh` is based on the opensource pdksh shell.

### Manually (addtofilecache)

You can add files to the local file catalog, these are then synced to the server's file inventory using the following command:

`--addtofilecache`

```
pmagent --privman --addfiletocache /usr/bin/id

pmagent --privman --addfiletocache /usr/bin/\*

pmagent --privman --addfiletocache /usr/bin/wh\*
```

## Deleting from Inventory (deletefilecache)

You can remove files from the local file catalog using the following command, these are not synced to the server's file inventory using the following command: 

`--deletefilecache`

```
pmagent --privman --deletefilecache

pmagent --privman --deletefilecache /usr/bin/id

pmagent --privman --deletefilecache /usr/bin/\*

pmagent --privman --deletefilecache /usr/bin/wh\*
```

## Listing Inventory (listfilecache)

You can list the local file inventory using the following command: 

`--listfilecache`

```
pmagent --privman --listfilecache

pmagent --privman --listfilecache /usr/bin/id

pmagent --privman --listfilecache /usr/bin/\*

pmagent --privman --listfilecache /usr/bin/wh\*
```

## Pushing to Privilege Manager Server

There is a scheduled task that will run every 30 second to check for local changes. In the event one is detected, information is sent to the server:

To review the Agent task list: `pmagent --list`

```
task: pmagent_processevents

        key:        default

        when:       2021-02-08 17:27:10

        reoccurs:   30s

        maxretries: forever

        backoff:    yes

        attempts:   0

        expires:    2262-04-12 00:47:16

        last tried: never
```
