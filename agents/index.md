[title]: # (Agents)
[tags]: # (endpoints)
[priority]: # (1900)
# Privilege Manager Agents

The [Privilege Manager Agents](../install/agents/index.md) are a critical component of Thycotic's application control and local security, giving you the ability to evaluate the health and status of endpoints in real time. Agents are required on endpoint machines to implement Privilege Manager policies.

Privilege Manager provides pre-configured and fully customizable reporting on the status of agents and endpoint operating systems. In the Privilege Manager reporting dashboard, you can drill into reports based on any dimension and easily export report data to other reporting applications or Excel.

Privilege Manager supports agents on:

* Windows
* macOS
* Unix/Linux

endpoint operating systems.

For information about installing agents, refer to [Agent Installation](../install/agents/index.md) to review agent system requirements and the specific agent installation procedures. This section of our document is a general agent information section, containing details about how to use/interact with agents and to provide information about the agent processes.

## Agent Hardening (Windows)

To make sure that local Administrators do not tamper with Thycotic agents running on their system, Privilege Manager Administrators can define users that can start and stop the Privilege Manager services running on endpoints, such as the Thycotic Agent or Thycotic Application Control. Refer to [Agent Hardening](win/agent-hardening.md).

## Post Agent Installation

When your agents are installed, you can verify the status of your Agents' health in terms of Registration State and Policy State from the Home page. You also can navigate to __Admin | Agents__ for more information about installed agents.

The Agent Health dials describe how many Managed Operating Systems you have as well as your Agent(s) Registration State and Policy State. If you click on the Agent Registration State dial, you will see a report on a list of machines (the "MonitoredResource" column) where each registered agent is installed.

Clicking the Agent Policy State dial from the Home dashboard brings you to a report that links all of your agent-registered machines with the Number of Policies Missing from each agent. This page will become invaluable once you have multiple policies running over different computer groups in your network.

## Diagnostics

Navigate to the __ADMIN | Diagnostics__ page to view more comprehensive agent details. The Diagnostics page also is the go-to stop for full system health. Go here to find Server Console Logs and other system level warnings or tips.

## Agent Encryption

The agent traffic is secured via SSL/TLS.

<!-- Post 10.7.1 release create a general agent section in the TOC to cover more general information and conceptual write-up. Remove this heading here and create more contents in that new agent section. -->