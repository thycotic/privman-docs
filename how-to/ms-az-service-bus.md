[title]: # (Azure Service Bus Configuration)
[tags]: # (create,set-up)
[priority]: # (9501)
# Azure Service Bus Configuration

Privilege Manager supports Internet connected clients through Microsoft Azure Service Bus. The Azure Service Bus is a subscription service that external agents can connect to and use to communicate with an internal Thycotic Management Server (TMS) instance. This document is broken up in three sections:

* Azure Services Bus Configuration
* TMS Services Bus Configuration
* Configuring the Agents to use the Service Bus

## Azure Service Bus Configuration

Thycotic requires a Service Bus relay for remote communication. To create a new Azure Service Bus, follow the procedure as outlined by Microsoft [here in Create a Service Bus namespace using the Azure portal](https://docs.microsoft.com/en-us/azure/service-bus-messaging/service-bus-create-namespace-portal).

## Setting up the Service Bus Foreign System

The Azure Service Bus requires a Foreign Systems configuration in Privilege Manager. To configure a Service Bus instance with a custom URL and credentials follow these steps:

1. In the Thycotic Privilege Manager Console, click __Admin | Configuration__.
1. Click the __User Credentials__ tab.
1. Click __Add New__ and select the newly created User Credential.
1. Set the Account name to RootManageSharedAccessKey and set the Password to the Shared Access Key (connection string) obtained during the Azure Service Bus configuration procedure.
1. Save the user credential and click __Back__.
1. Select the __Foreign Systems__ tab and click the Azure Service Bus option.
1. Click __Add New__.
1. Set the Name to any name that you want and set the ServiceBus Name to the namespace created during the Azure Configuration procedure.
1. Click __Create__.
1. Set the credential to the credential created in step 5 of this procedure.
1. Enable the Service Bus
   1. Make sure the URI matches the namespace in Azure.
   1. Set the QueueName to the same queue name used in the Azure Configuration.
   1. Set the Queue Policy Name to RootManageSharedAccessKey.
   1. Set the Queue Policy Secret to the Shared Access Key as obtained in the Azure Service Bus configuration procedure (also used in step 4 above).
1. Click Save.
1. Recycle the TmsWorker application application pool for the new settings to be applied.

## Configuring Agents to Use the Service Bus

Agents require a Privilege Manager Server to communicate with. The recommended way to set the URL address is during the installation of the Thycotic Agent by setting the TMSURL parameter. The TMS address can be changed post-install via the registry or PowerShell.

### Setting the Privilege Manager Server (TMS) Address via the Registry Editor

1. Open the Registry Editor (regedit)
1. Navigate to __HKEY_LOCAL_MACHINE | SOFTWARE | Policies | Arellia | AMS__.
1. Right click BaseUrl and select Modify.
1. In the Edit String dialog box, change the BaseURL to your TMS Address based on the Azure Service Bus configuration.
1. Close the registry.
1. Restart the Agent service.

### Setting the Privilege Manager Server (TMS) Address via PowerShell

To set the TMS address via PowerShell, run this command as Administrator:

```ps1
C:\Program Files\Thycotic\Powershell\Arellia.Agent\SetAmsServer.ps1
```

The script will then ask you to type in the fully qualified domain name of the server.
