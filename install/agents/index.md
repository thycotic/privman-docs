[title]: # (Agent Installation)
[tags]: # (Endpoint,Agent Installation)
[priority]: # (1600)
# Agent Installation

Agents are required on endpoint machines to carry out policies created in Privilege Manager. This page offers direct downloads and descriptions for all available agents.

Agents are required on endpoint machines to implement Privilege Manager policies. Thycotic Agents can be deployed in various ways: software management systems, GPO, cloned (gold) images, and manually. Instructions and links for agent installers are provided in this article, grouped as follows:

* [Bundled Agent Installer - Windows](agent-inst-win-bundle.md)
* Individual Agent Installers for Privilege Manager:
  * [64-bit Windows Operating Systems](agent-inst-win.md#64_bit_windows_operating_systems)
  * [32-bit Windows Operating Systems](agent-inst-win.md#32_bit_windows_operating_systems)
* [macOS X Installer - 10.11 or Newer](agent-inst-mac.md#installing_macos_agents)

For details about Thycotic Agent System Requirements, see our Privilege Manager System Requirements Guide here.

## Post Agent Installation

When your agents are installed, you can verify the status of your Agents’ health in terms of Registration State and Policy State from the Home page. You also can navigate to Admin | Agents for more information about installed agents.

The Agent Health dials describe how many Managed Operating Systems you have as well as your Agent(s) Registration State and Policy State. If you click on the Agent Registration State dial, you will see a report on a list of machines (the “MonitoredResource” column) where each registered agent is installed.

Clicking the Agent Policy State dial from the Home dashboard brings you to a report that links all of your agent-registered machines with the Number of Policies Missing from each agent. This page will become invaluable once you have multiple policies running over different computer groups in your network.

## Diagnostics

Navigate to the __ADMIN | Diagnostics__ page to view more comprehensive agent details. The Diagnostics page also is the go-to stop for full system health. Go here to find Server Console Logs and other system level warnings or tips.
