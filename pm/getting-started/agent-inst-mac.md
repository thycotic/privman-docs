[title]: # (Agent Installation Mac)
[tags]: # (Endpoint,Agent Installation,Registration,Mac)
[priority]: # (232)
# Agent Installation Mac OSx Systems

## Mac OS X Installer (10.11 or Newer)

The Bundled Mac Agent DMG + PKG installer is available for Mac machines. You can use this installer directly on individual endpoints for testing or for production environments.

### Privilege Manager Mac Agent
<!-- TODO: Version update -->
https://tmsnuget.thycotic.com/Software/Agents/ThycoticManagementAgent-10.5.12.dmg

### Installating Mac Agent Directly

The Bundled Mac Agent is a DMG + PKG file. You can use this Mac agent installer directly on individual endpoints for testing or production environments.

To install the Thycotic agents on a single testing machine, follow these steps:
1. Go to Agent Downloads and download the Privilege Manager Mac Agent.
1. Run the Bundled Mac Agent DMG + PKG Installer on the computer you want to manage.
1. During the setup process,
   1. enter the base URL and
   1. the Install Code when prompted.​

>[!Note]
>The Install Code field can be left blank when using versions lower than 10.5.

<User-added image>

### Deploying Agents using an Unattended Install Method

Begin by downloading the DMG + PKG package (See link for Privilege Manager Mac Agent listed above) on one of your Mac endpoints. Run the installer by double clicking the PKG file.  

After installing this first agent, navigate to _/Library/Application Support/Thycotic/Agent/agentconfig.json_. The agentconfig.json file stores information such as your organization’s URL and a few other custom settings like ‘Task Polling Interval,’ etc.

Open the file and add the "installCode" parameter after the "tmsBaseUrl" to that file as shown in the following code sample:
 
```json
{
                "tmsBaseUrl": "https://servername/Tms/"",
                "installCode": "VALUEHERE"
}
```

>[!Note]
>The Install Code can be left blank when using versions lower than 10.5

There are two methods for deploying your remaining mac agents in an unattended fashion:

* Network File Share
* Distribution Tool  

#### Network File Share

If you want to use administrators to deploy agents onto individual mac endpoints, save the PKG installer side-by-side with the agentconfig.json file in a network share folder. Users/Administrators can then run the installation (PKG) from that folder onto each endpoint.  

The PKG will first look for an agentconfig.json file located in the same folder. When it finds this file, it will copy agentconfig.json into the /Library/Application Support/Thycotic/Agent folder during the unattended install on the Mac endpoint where the installer is running.

#### Distribution Tool

Using a Deployment Tool like Jamf or SCCM, include both the PKG installer and the agentconfig.json files in the distribution package together, then deploy the package onto your endpoint macs by running a script using a tool or remotely by using ssh to install the PKG (eg. ```sudo installer -pkg ThycoticManagementAgent.10.4.14.pkg -target /```).  

As in the example using a Network Share, the PKG will first look for an agentconfig.json file located in the same folder. When it finds this file, it will copy agentconfig.json into the /Library/Application Support/Thycotic/Agent folder during the unattended install on the endpoint Mac where the installer is running.

For more instructions on how to deploy in bulk using Microsoft Software System Center Configuration Manager (SCCM), Microsoft instructions for Macs are described here. 

## After Initial Deployment

If the Mac already has an existing agentconfig.json file, it will NOT be overwritten because creating a file only occurs if the computer didn’t already have an agentconfig.json installed. This means you can use the same distribution package for upgrades and new installs.

>[!Note]
>It will take 15-30 minutes for newly installed agents to register in Privilege Manager, and policies will update according to a scheduled task in Privilege Manager. To check the schedule on this task, go to Admin | Resources | [Select Mac Machine Name] | "Update Agent Commands (Mac OS)" Policy | Triggers tab. 
>To register agents immediately, see instructions in the Terminal Commands section.

## Register New Agents and Finding Logs for Troubleshooting

For troubleshooting your Mac agent, logs are found in the Console application. There are two places to check for logs in Console:

* First, you can filter your machine's logs by clicking your machine's name under Devices and typing "Thycotic" into the top search bar.
* Second, Thycotic-specific logs are recorded in a Console folder that is titled thycotic (found in the left side bar: Reports > /var/log > thycotic).

### Terminal Commands

In the Mac Terminal application you can perform the following commands directly to your Thycotic Mac agent. Find this list by entering: 

```shell
sudo /usr/local/thycotic/agent/agentUtil.sh
```

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

#### Command Usage

To perform a command, insert the name of the above command that you need to perform into this command string:  

```shell
sudo /usr/local/thycotic/agent/agentUtil.sh [InsertCommandHere]
```

As one example, if you entered an incorrect server name path in the agent installer and Privilege Manager therefore cannot find and register your Mac agent, you can run the command:
  
```shell
sudo /usr/local/thycotic/agent/agentUtil.sh settmsserver -serverUri {https://servername.com/Tms/}
```

using the correct server name uri to redirect your agent toward the correct server location.

Or, to register an agent immediately after updating the Privilege Manager server location, type:

```shell
sudo /usr/local/thycotic/agent/agentUtil.sh register
```

   ![Agent Registration via Terminal Command](/images/agent/mac-man-reg.png)
