[title]: # (Agent Installation Windows)
[tags]: # (Endpoint,Agent Installation,Windows)
[priority]: # (231)
## Agent Installation on Windows Systems

## Bundled Privilege Manager Agent Installer

This bundled EXE installer is recommended when installing Privilege Manager on machines one at a time, for deployments through software delivery see the next section. This installer includes all Privilege Manager Agents for Windows machines (Core, ACS, LSS). You can use this installer directly on individual endpoints for testing or for production environments in either 32-bit or 64-bit environments: <!-- TODO: Version update -->

* Bundled Agent Installer: https://tmsnuget.thycotic.com/Software/Agents/ThycoticAgentsInstaller_x86_10_5_1029.exe

## Individual Agent Installers for Privilege Manager

### 64-bit Windows Operating Systems

Individual Windows agents are available in MSI format for easier bulk-rollout through software delivery tools. For installing individual agents, begin with the Core Thycotic Agent:

* __Core Thycotic Agent (x64)__:
  https://tmsnuget.thycotic.com/Software/Agents/ThycoticAgent_x64_10_5_1029.msi
* __Application Control Agent (x64)__:
  https://tmsnuget.thycotic.com/Software/Agents/Thycotic_ApplicationControlAgent_x64_10_5_1033.msi
* __Local Security Solution Agent (x64)__:
  https://tmsnuget.thycotic.com/Software/Agents/Thycotic_LocalSecurityAgent_x64_10_5_1027.msi

#### Installation Command Lines

>**Note**:
>The Install Code field can be left blank when using versions lower than 10.5

* __Core Thycotic Agent__
  ```
  msiexec.exe /i "ThycoticAgent_x64_10_5_1029.msi" /norestart AMSURL=https://SERVERNAME/TMS/ INSTALLCODE=XXXX1234ABCD REBOOT=ReallySuppress /qn
  ```
* __Application Control Agent__
  ```
  msiexec.exe /i "Thycotic_ApplicationControlAgent_x64_10_5_1033.msi" /norestart REBOOT=ReallySuppress /qn
  ```
* __Local Security Agent__
  ```
  msiexec.exe /i "Thycotic_LocalSecurityAgent_x64_10_5_1027.msi" /norestart REBOOT=ReallySuppress /qn
  ```

### 32-bit Windows Operating Systems

Individual Windows agents are available in MSI format for easier bulk-rollout through software delivery tools. For installing individual agents, begin with the Core Thycotic Agent:

* Core Thycotic Agent __(x86)__:
  https://tmsnuget.thycotic.com/Software/Agents/ThycoticAgent_x86_10_5_1029.msi
* Application Control Agent __(x86)__:
  https://tmsnuget.thycotic.com/Software/Agents/Thycotic_ApplicationControlAgent_x86_10_5_1033.msi
* Local Security Solution Agent __(x86)__:
  https://tmsnuget.thycotic.com/Software/Agents/Thycotic_LocalSecurityAgent_x86_10_5_1027.msi

#### Installation Command Lines

>**Note**:
>The Install Code field can be left blank when using versions lower than 10.5

* Core Thycotic Agent
  ```
  msiexec.exe /i "ThycoticAgent_x86_10_5_1029.msi" /norestart AMSURL=https://SERVERNAME/TMS/ INSTALLCODE=XXXX1234ABCD REBOOT=ReallySuppress /qn
  ```
* Application Control Agent
  ```
  msiexec.exe /i "Thycotic_ApplicationControlAgent_x86_10_5_1033.msi" /norestart REBOOT=ReallySuppress /qn
  ```
* Local Security Agent
  ```
  msiexec.exe /i "Thycotic_LocalSecurityAgent_x86_10_5_1027.msi" /norestart REBOOT=ReallySuppress /qn
  ```