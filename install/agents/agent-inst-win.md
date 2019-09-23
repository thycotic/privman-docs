[title]: # (- Windows Agents)
[tags]: # (endpoint,installation)
[priority]: # (602)
# Windows Agents

Use the links below to download the agent installation software for Windows based endpoints.

There are three agents available for Windows endpoints:

* Thycotic Agent: The core agent is responsible for all reporting and monitoring communication on the endpoint. It can be considered the managing agent, while the Application Control and Local Security Agents are the worker agents.
* Application Control Agent (ACS): This agent is responsible for monitoring processes executing the Privilege Manager Application Control Functions on the endpoint.
* Local Security Agent (LSS): This agent is responsible for monitoring and executing Local Security functions.

## Bundled Privilege Manager Agent Installer

This bundled EXE installer is recommended when installing Privilege Manager on machines one at a time, for deployments through software delivery see the next section. This installer includes all Privilege Manager Agents for Windows machines (Core, ACS, LSS). You can use this installer directly on individual endpoints for testing or for production environments in either 32-bit or 64-bit environments:

* Bundled Agent Installer: https://tmsnuget.thycotic.com/software/Agents/ThycoticAgentsInstaller_x86_10_6_1080.exe

## Individual Agent Installers for Privilege Manager

### 64-bit Windows Operating Systems

Individual Windows agents are available in MSI format for easier bulk-rollout through software delivery tools. For installing individual agents, begin with the Core Thycotic Agent:

* __Core Thycotic Agent (x64)__:
  https://tmsnuget.thycotic.com/software/Agents/ThycoticAgent_x64_10_6_1080.msi
* __Application Control Agent (x64)__:
  https://tmsnuget.thycotic.com/software/Agents/Thycotic_ApplicationControlAgent_x64_10_5_1080.msi
* __Local Security Solution Agent (x64)__:
  https://tmsnuget.thycotic.com/software/Agents/Thycotic_LocalSecurityAgent_x64_10_6_1025.msi

#### Installation Command Lines

>**Note**:
>The Install Code field can be left blank when using versions lower than 10.5

* __Core Thycotic Agent__
  ```
  msiexec.exe /i "ThycoticAgent_x64_10_6_1080.msi" /norestart AMSURL=https://SERVERNAME/TMS/ INSTALLCODE=XXXX1234ABCD REBOOT=ReallySuppress /qn
  ```
* __Application Control Agent__
  ```
  msiexec.exe /i "Thycotic_ApplicationControlAgent_x64_10_6_1080.msi" /norestart REBOOT=ReallySuppress /qn
  ```
* __Local Security Agent__
  ```
  msiexec.exe /i "Thycotic_LocalSecurityAgent_x64_10_6_1025.msi" /norestart REBOOT=ReallySuppress /qn
  ```

### 32-bit Windows Operating Systems

Individual Windows agents are available in MSI format for easier bulk-rollout through software delivery tools. For installing individual agents, begin with the Core Thycotic Agent:

* Core Thycotic Agent __(x86)__:
  https://tmsnuget.thycotic.com/software/Agents/ThycoticAgent_x86_10_6_1080.msi
* Application Control Agent __(x86)__:
  https://tmsnuget.thycotic.com/software/Agents/Thycotic_ApplicationControlAgent_x86_10_6_1080.msi
* Local Security Solution Agent __(x86)__:
  https://tmsnuget.thycotic.com/software/Agents/Thycotic_LocalSecurityAgent_x86_10_6_1025.msi

#### Installation Command Lines

>**Note**:
>The Install Code field can be left blank when using versions lower than 10.5

* Core Thycotic Agent
  ```
  msiexec.exe /i "ThycoticAgent_x86_10_6_1080.msi" /norestart AMSURL=https://SERVERNAME/TMS/ INSTALLCODE=XXXX1234ABCD REBOOT=ReallySuppress /qn
  ```
* Application Control Agent
  ```
  msiexec.exe /i "Thycotic_ApplicationControlAgent_x86_10_6_1080.msi" /norestart REBOOT=ReallySuppress /qn
  ```
* Local Security Agent
  ```
  msiexec.exe /i "Thycotic_LocalSecurityAgent_x86_10_6_1025.msi" /norestart REBOOT=ReallySuppress /qn
  ```
