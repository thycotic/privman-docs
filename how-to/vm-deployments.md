[title]: # (VM Delopyments)
[tags]: # (virtual machines)
[priority]: # (9510)
# VM Deployments

Privilege Manager agents are installed on endpoint machines to implement policies which are defined by the user (the Privilege Manager administrator) in the Privilege Manager console (the user interface of the Privilege Manager Server).

This article is about agent deployment to endpoints in Virtual Desktop Infrastructure (VDI) or other similar environments. It describes the different cases and options for deploying Privilege Manager agents to VDIs and discusses the pros and cons where relevant. It is expected to be read by a user who is the Privilege Manager administrator for the customer.

Installing the Privilege Manager agent is supported as part of a VDI image build. There are a few different ways to accomplish this, based on the (Privilege Manager) customer’s environment and preferences. Discussion of the relevant issues and options is grouped in this article as follows:

## Identifying Agents to The Console

The pertinent question here is: Do you (the user) plan to use (or are using) persistent virtual machines (VMs) or dynamic VMs? There are different implications for each of these, discussed below.
 
### Persistent VMs 
In a persistent VM, machines images are created, spun up, and then persist indefinitely. This case is fairly simple.  We can treat these machines the same as we would physical machines except for concerns around the universally unique identifier (UUID), which will be discussed further on (in the section, “Multiple VMs Collapsed to a Single Resource”).
 
### Dynamic VMs
In a dynamic VM, a golden image is spun up each time a user requests it with their profile and it is then applied on top. This case is more complicated.
 
The major concern is agent spamming, which would happen as follows: the Privilege Manager console sees each new image as a new computer and rapidly runs through the customer’s licenses, leaving a large number of orphan machines. There are a few different ways to deal with this situation, discussed in the sub-sections below.
 
### Multiple VMs Collapsed to a Single Resource

The easiest way to support dynamic VMs is for you to collapse all of your VMs to a single computer resource on the console.  This can be accomplished as follows:
1. Add a registry entry in HKLM\Software\Arellia\Agent called “AgentIdOverride.”
1. Install the agent on a physical computer and allow it to register.
1. Next, in the Privilege Manager console:
   1. Navigate to Admin > Agents.
   1. Click on one of the charts to view a list of registered computers.
   1. Find the computer in the report and click on it. This will take you to the Resource View of that computer. The ID for this computer is the UUID displayed as the last part of the URL (after “/item/view/”) in the browser address bar.
   1. Copy this ID value (the last part of the browser URL).
1. Place the copied ID value in the AgendIdOverride registry entry.

Alternatively, if you want multiple VDI images to which differing policy sets are applied, you could have different values. The rollup computers in the console could then be assigned to the appropriate resource targets.
 
The benefits of this approach are:

* It is by far the simplest to implement.
* It results in the fewest licensing issues.
* Moreover, because the resources are created ahead of time they can be inventoried and assigned to the appropriate resource targets. Consequently, a machine would get the appropriate policies as soon as it spins up with no need to wait for processes to run either on the desktop or server.
 
The downside of this approach is:

* There would be some loss of fidelity in data on the console, specifically around which machine an event happened on.  However, since virtual desktops are by nature transitory that may be less of a concern.  Privilege Manager will still attach usernames to the event data so you will know “who” (the end user) if not necessarily “where” (the specific endpoint).
 
#### Pool of Values to Support Multiple VMs

If you wish to be more specific, the following technique could be used: create a pool of UUID values to be assigned to the AgentIDOverride and assign one from this pool when the machine spins up.
 
With this technique, as part of the VDI provisioning, Privilege Manager would trigger the basic inventory task to make sure that the server gets correct information on the machine name and details. You would want a pool of values rather than a random one to prevent spamming new agents. Reusing the values would keep that under control. 
 
## Managing Agent Trust and Certificates

This section discusses certificate management. 
 
As of version 10.5, Privilege Manager validates agent certificates against the specific agent that was initially registered. There are two cases:
 
* All desktops using a single agentID: This case is fairly straightforward.  A single certificate would be included as part of the desktop image which would match what was stored in the database for that ID and all of the communication would be accepted.
* A pool of IDs: In this case, there are two potential ways to do certificate management:

  * Method 1: Navigate to Admin > Configuration > Advanced; select the "Allow Agent Certificate Mismatch" option; turn on the option. (It is off by default.)
  * Method 2: Deploy the install code on machine imaging, as follows:

    * Add a registry entry in HKLM\Software\Arellia\Agent of type String and call it “InstallCode.”
    * In the Privilege Manager console:

      * Navigate to Admin > Agents > “Installation Codes” tab.
      * Click “Copy” to copy the value displayed under Code.
    * Paste the copied value into the InstallCode registry entry.
    * Once this entry is set, then during the agent registration process, the agent sends this InstallCode up to the server along with whatever certificate it has. This overrides the database entry and allows that agent to communicate as long as it is up and running. 
 
## Minimizing Time Between VDI Deployment and Policy Enforcement

This section is about policy deployment.
 
In a non-VDI environment, when Privilege Manager deploys agents to desktops, there can be a significant delay between deployment and policy enforcement and it is not a concern because it is a one-time issue.
 
However, in the case of VDI, machines are created and recreated daily and this delay becomes a larger issue. In this case, you must make sure that the Client Items database, with the appropriate policies, is part of the initial desktop image. This file can be created in C:\ProgramData\Arellia\ClientItems and can be simply copied from a machine that has the agent deployed and all policies downloaded. 
 
However, if any policy changes are made after image creation you would need to either update that file in the golden image or add a post-deployment step to run the Powershell script “C:\Program Files\Thycotic\Powershell\Arellia.Agent\UpdateClientItems.ps1” and trigger the virtual desktop to download the latest policy items. 
 
## Licensing Concerns with Windows 10 Amazon Workspaces

This section discusses licensing concerns, specifically with Windows 10 Amazon Workspaces.
 
Although Amazon claims to offer a Windows 10 VDI environment, what they offer is not technically speaking Windows 10. Rather, what they provide is a Windows Server 2016 environment running what they call Windows 10 Experience.
 
This means that when Privilege Manager inventories it, the Privilege Manger agent believes that it is running on a server class OS. Therefore, from a licensing perspective, Amazon Workspaces need to be licensed as servers, rather than as clients.
