[title]: # (Setting Server Address)
[tags]: # (agent set-up)
[priority]: # (2)
# Setting the Privilege Manager Server Address

Agents require a Privilege Manager Server to communicate with. The recommended way to set the URL address is during the [installation of the Thycotic Agent](../../install/agents/index.md). If an Azure Service Bus or Reverse Proxy is used, the URL can point at the URL of those components.

The URL address can be changed post-install via the registry or PowerShell.

## Setting the Privilege Manager Server (TMS) Address via PowerShell

To set the Privilege Manager Server (TMS) address via PowerShell, run this command as Administrator:

```ps1
C:\Program Files\Thycotic\Powershell\Arellia.Agent\SetAmsServer.ps1
```

The script will then ask you to type in the fully qualified domain name of the server.

## Changing the Privilege Manager Server (TMS) Address via the Registry Editor

1. Open the Registry Editor (regedit)
1. Navigate to __HKEY_LOCAL_MACHINE | SOFTWARE | Policies | Arellia | AMS__.
1. Right click BaseUrl and select Modify.

   ![BaseUrl in Registry Editor](images/base-url.png)
1. In the Edit String dialog box, change the BaseURL to your TMS Address.
1. Close the registry.
1. Restart the Agent service.
