[title]: # (Windows Agents)
[tags]: # (endpoint,installation)
[priority]: # (1603)
# Windows Agents

Use the links below to download the agent installation software for Windows based endpoints.

There are three agents available for Windows endpoints:

* __Thycotic Agent__: The core agent is responsible for all reporting and monitoring communication on the endpoint. It can be considered the managing agent, while the Application Control and Local Security Agents are the worker agents.
* __Application Control Agent__ (ACS): This agent is responsible for monitoring processes executing the Privilege Manager Application Control Functions on the endpoint.
* __Local Security Agent__ (LSS): This agent is responsible for monitoring and executing Local Security functions.

## Individual Agent Installers for Privilege Manager

### Hardened Agents

If agent hardening was applied to user endpoints, the hardened agents need to be deleted via the `sc delete {agent name}` commandline command. This needs to be done under the context of the domain user prior to running the msi-based agent installation commands. When the agent is deleted successfully, a success message will be returned, for example:

```cmd
C:\sc delete arelliaagent
[SC] DeleteService SUCCESS
C:\sc delete arelliaacsvc
[SC] DeleteService SUCCESS
```

>**Note**: If the hardened agents are being deleted via software delivery script, the script needs to be delivered under the context of the domain user.

### 64-bit Windows Operating Systems

Individual Windows agents are available in MSI format for easier bulk-rollout through software delivery tools. For installing individual agents, begin with the Core Thycotic Agent:

* __Core Thycotic Agent (x64)__:
  https://tmsnuget.thycotic.com/software/Agents/ThycoticAgent_x64_10_7_2219.msi
* __Application Control Agent (x64)__:
  https://tmsnuget.thycotic.com/software/Agents/Thycotic_ApplicationControlAgent_x64_10_7_2239.msi
* __Local Security Solution Agent (x64)__:
  https://tmsnuget.thycotic.com/software/Agents/Thycotic_LocalSecurityAgent_x64_10_7_2219.msi

#### Installation Command Lines

>**Note**:
>The Install Code field can be left blank when using versions lower than 10.5

* __Core Thycotic Agent__
  ```
  msiexec.exe /i "ThycoticAgent_x64_10_7_2219.msi" /norestart AMSURL=https://SERVERNAME/TMS/ INSTALLCODE=XXXX1234ABCD REBOOT=ReallySuppress /qn
  ```
* __Application Control Agent__
  ```
  msiexec.exe /i "Thycotic_ApplicationControlAgent_x64_10_7_2239.msi" /norestart REBOOT=ReallySuppress /qn
  ```
* __Local Security Agent__
  ```
  msiexec.exe /i "Thycotic_LocalSecurityAgent_x64_10_7_2219.msi" /norestart REBOOT=ReallySuppress /qn
  ```

### 32-bit Windows Operating Systems

Individual Windows agents are available in MSI format for easier bulk-rollout through software delivery tools. For installing individual agents, begin with the Core Thycotic Agent:

* Core Thycotic Agent __(x86)__:
  https://tmsnuget.thycotic.com/software/Agents/ThycoticAgent_x86_10_7_2219.msi
* Application Control Agent __(x86)__:
  https://tmsnuget.thycotic.com/software/Agents/Thycotic_ApplicationControlAgent_x86_10_7_2239.msi
* Local Security Solution Agent __(x86)__:
  https://tmsnuget.thycotic.com/software/Agents/Thycotic_LocalSecurityAgent_x86_10_7_2219.msi

#### Installation Command Lines

>**Note**:
>The Install Code field can be left blank when using versions lower than 10.5

* Core Thycotic Agent
  ```
  msiexec.exe /i "ThycoticAgent_x86_10_7_2219.msi" /norestart AMSURL=https://SERVERNAME/TMS/ INSTALLCODE=XXXX1234ABCD REBOOT=ReallySuppress /qn
  ```
* Application Control Agent
  ```
  msiexec.exe /i "Thycotic_ApplicationControlAgent_x86_10_7_2239.msi" /norestart REBOOT=ReallySuppress /qn
  ```
* Local Security Agent
  ```
  msiexec.exe /i "Thycotic_LocalSecurityAgent_x86_10_7_2219.msi" /norestart REBOOT=ReallySuppress /qn
  ```
