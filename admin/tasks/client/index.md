[title]: # (Client Tasks)
[tags]: # (default)
[priority]: # (1)
# Client Tasks

Client Tasks are used to run or schedule activities at the endpoints, like:

* Basic Inventory, which triggers the agent to immediately report basic inventory back to the server. The information can be viewed for a computer under Known Data. Data sets are different based on endpoint operating system.
* Resource Discovery Client Task, which populates agent-side data for any resources that have been discovered but lack detailed information.
* Update Applicable Policies, which triggers policy updates at the endpoints.

>**Note**: All default enabled client tasks __are read-only items__ and if any customization to the schedule is required, create a copy to add, save, and apply changes. Schedule changes can be added on the Triggers page when clicking the existing schedule and then __Show Advanced__.

Details for each tasks are provided under the following topics:

* [Basic Inventory](bi.md)
* [Cleanup Agent Inventory Transfer](cait.md)
* [COM Inventory Policy](cip.md)
* [Cleanup Sent Privilege Manager Event](cpme.md)
* [Configure PM Remove Programs](cpmrp.md)
* [Default File Inventory Policy](dfip.md)
* [Deploy File Hash Exclusion Setting (Windows)](exclude-from-file-hash.md) - installed via Configuration Feeds only!
* [Ensure UAC Override Setting](euacos.md)
* [Ignore macOS Catalina software update (Mac OS)](ignore-os-updates.md) - installed via Configuration Feeds only!
* [Local User Inventory Policy](luip.md)
* [Perform Resource Discovery](prd.md)
* [Reset ignored macOS software updates (Mac OS)](ignore-os-updates.md) - installed via Configuration Feeds only!
* [Retry Errored TMS Events](retmse.md)
* [Set Agent Log Size](sals.md)
* [Scheduled Check for Pending Tasks](scfpt.md)
* [Shared Folder Inventory Policy](sfic.md)
* [Scheduled Registration](sr.md)
* [Update Agent Commands](uac.md)
* [Update Applicable Policies](uap.md)
* [User Logon Inventory Policy](ulip.md)
* [Update Provisioned Resource Client Items](uprci.md)
* [Windows Server Inventory Policy](wsip.md)