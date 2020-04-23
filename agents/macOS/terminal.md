[title]: # (Terminal Commands)
[tags]: # (endpoints)
[priority]: # (3)
# Terminal Commands

In the Mac Terminal application you can perform the following commands directly to your Thycotic macOS agent.

>**Note**: The `sudo` command may prompt for admin account password verification.

Find this list by entering the following into Terminal:

```shell
sudo /usr/local/thycotic/agent/agentUtil.sh
```

These are the commands returned for the utility:

```shell
runschedule -scheduleId {id}
updateclientitems
clientitemsummary
register
settmsserver -serverUri {https://servername.com/Tms/}
settmsserver -serverName {servername}
stop
start
restart
enableverboselogging
disableverboselogging
```

## Command Usage

To perform a command, insert the name of the above command that you need to perform into this command string:  

```shell
sudo /usr/local/thycotic/agent/agentUtil.sh [InsertCommandHere]
```

As one example, if you entered an incorrect server name path in the agent installer and Privilege Manager therefore cannot find and register your Mac agent, you can run the command:
  
```shell
sudo /usr/local/thycotic/agent/agentUtil.sh settmsserver -serverUri {https://servername.com/Tms/}
```

Which is using the correct server name URI to redirect your agent toward the correct server location.

Or, to register an agent immediately after updating the Privilege Manager server location, type:

```shell
sudo /usr/local/thycotic/agent/agentUtil.sh register
```

The complete command shell exchange looks like this:

```shell
macadmin-MacBook-Pro:~ madadmin$ sudo /usr/local/thycotic/agent/agentUtil.sh register
Password:
Initiated registration.
macadmin-MacBook-Pro:~ madadmin$
```
