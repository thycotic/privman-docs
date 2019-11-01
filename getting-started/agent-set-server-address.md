[title]: # (Setting the Privilege Manager Server Address)
[tags]: # (agent set-up)
[priority]: # (1600)
# Setting the Privilege Manager Server Address

Agents require a Privilege Manager Server to communicate with. The recommended way to set the URL address is during the installation of the Thycotic Agent by setting the TMSURL parameter. The TMSURL can be pointing directly to your Privilege Manager instance or if an Azure Service Bus or Reverse Proxy is used, it can be created to point at the URL of those components. Privilege Manager can’t push tasks to Internet-connected clients, but the agents will automatically check every hour for tasks that they need to run.

The TMSURL address can be changed post-install via the registry or PowerShell.

## Changing the Privilege Manager Server (TMS) Address via the Registry Editor

1. Open the Registry Editor (regedit)
1. Navigate to __HKEY_LOCAL_MACHINE | SOFTWARE | Policies | Arellia | AMS__.
1. Right click BaseUrl and select Modify.

   ![BaseUrl in Registry Editor](images/base-url.png)
1. In the Edit String dialog box, change the BaseURL to your TMS Address.
1. Close the registry.
1. Restart the Agent service.

## Setting the Privilege Manager Server (TMS) Address via PowerShell

To set the Privilege Manager Server (TMS) address via PowerShell, run this command as Administrator:

```ps1
C:\Program Files\Thycotic\Powershell\Arellia.Agent\SetAmsServer.ps1
```

The script will then ask you to type in the fully qualified domain name of the server.
