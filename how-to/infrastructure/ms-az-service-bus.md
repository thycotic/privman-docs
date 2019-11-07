[title]: # (Azure Service Bus Configuration)
[tags]: # (create,set-up)
[priority]: # (2)
# Azure Service Bus Configuration

Privilege Manager supports Internet connected clients through Microsoft Azure Service Bus. The Azure Service Bus is a subscription service that external agents can connect to and use to communicate with an internal Privilege Manager Server (TMS) instance. This document is broken up in three sections:

* Azure Services Bus Queue Configuration
* Setting up the Service Bus as a Foreign System in Privilege Manager
* Configuring the Agents to use the Service Bus (if this is a new agent installation, the Agents can be pointed directly at the Service Bus namespace URL)

With Privilege Manager 10.7 and up TLS 1.2 is supported.

## Azure Service Bus Queue Configuration

Thycotic requires a Service Bus relay for remote communication. For this a Service Bus Queue needs to be created, follow the procedure as outlined by Microsoft [here in Quickstart: Use Azure portal to create a Service Bus queue](https://docs.microsoft.com/en-us/azure/service-bus-messaging/service-bus-quickstart-portal).

The Service Bus Namespace URL created in Azure needs to be used when setting the URL for Agent communication under the [Configuring Agents to Use the Service Bus](https://dev.homer.thycotic.net/privman/0.1.0-dev/how-to/ms-az-service-bus.md#configuring-agents_to_use_the_service-bus) heading.

## Setting up the Service Bus Foreign System

The Azure Service Bus requires a Foreign Systems configuration in Privilege Manager. To configure a Service Bus instance with a custom URL and credentials follow these steps:

1. In the Thycotic Privilege Manager Console, click __Admin | Configuration__.
1. Click the __User Credentials__ tab.
1. Click __Add New__ and enter a __Name__, click __Create__.
1. Select the newly created User Credential.
1. Set the Account name to RootManageSharedAccessKey and set the Password to the Shared Access Key (connection string) obtained during the Azure Service Bus configuration procedure.
1. Save the user credential and click __Back__.
1. Select the __Foreign Systems__ tab and click the Azure Service Bus option.
1. Click __Add New__.
1. Set the Name to any name that you want and set the ServiceBus Name to the namespace created during the Azure Configuration procedure.
1. Click __Create__.
1. Set the credential to the credential created in step 5 of this procedure.
1. Enable the Service Bus
   1. Make sure the URI matches the first part of the namespace created in Azure.
   1. Set the QueueName to the same queue name used in the Azure Configuration.
   1. Set the Queue Policy Name to RootManageSharedAccessKey.
   1. Set the Queue Policy Secret to the Shared Access Key as obtained in the Azure Service Bus configuration procedure (also used in step 4 above).
1. Click Save.
1. Recycle the TmsWorker application pool for the new settings to be applied.

## Configuring Agents to Use the Service Bus

>**Note**:
>For new installations, the agents can be set up to communicate with the service bus during the initial installation process when the TMSURL and installation codes are provided, refer to [Bundled Install](../install/agent-inst-win-bundle.md).

### Using regedit

1. Open the Registry Editor (regedit)
1. Navigate to __HKEY_LOCAL_MACHINE | SOFTWARE | Policies | Arellia | AMS__.
1. Right click BaseUrl and select Modify.
1. In the Edit String dialog box, change the BaseURL to your Privilege Manager (TMS) Address based on the __Azure Service Bus Queue__ configuration, for example `https://[your company].servicebus.windows.net/`, which in our example is `https://testing.servicebus.windows.net/`
1. Close the registry.
1. Restart the Agent service.

### Using PowerShell

To modify the TMS address via PowerShell, run this command as Administrator:

```ps1
C:\Program Files\Thycotic\Powershell\Arellia.Agent\SetAmsServer.ps1
```

The script will then ask you to type in the fully qualified domain name of the server, enter the __Azure Service Bus Queue URL__.
