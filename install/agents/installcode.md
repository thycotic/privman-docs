[title]: # (Agent Install Codes)
[tags]: # (agent,endpoint)
[priority]: # (1601)
# Agent Install Codes

In version 10.5 and up, installation codes are required upon initial install to prove to the server that an agent install is authorized. Once an agent is installed, it deletes the install code and authenticates to the server via a certificate. See Agent Trust Revocation for certificate revocation.

The agent uses the install code to prove to the server that it is an authorized install. Once the agent is installed, the install code is deleted and the agent certificate is used to communicate with the server. The server needs either an install code or agent trust (a certificate) to accept communication from an agent. Multiple install codes can be created for bundling with different installers, if the last install code is revoked, a new one is generated automatically. Revoking an install code prevents new installations with that install code but does not affect previous installations since those agents now use their own certificates to authenticate.

1. Navigate to the agent settings under __Admin | Agents__.
1. On the Installation Codes tab you may Generate New codes, Refresh code information, Revoke, or Copy Codes to the clipboard to use in the installer.

   ![Installation Codes tab](images/codes.png)

If deploying with msiexec, the following command shows an example for how to set the Install Code:

```cmdline
msiexec.exe /i ThycoticTmsSetup_x64.msi INSTALLCODE=1234XXXXABCD AMSURL=https://DOMAIN/Name/
```

Where:

* ThycoticTmsSetup_x64 is the install file used.
* INSTALLCODE is argument taking the install code value.
* AMSURL is the argument taking the base URL to the TMS installation.

If installing via a bundled installer, the install code is placed in the __Enter the Install Code__ field (dashes in the install code are for readability and are optional).

![Installation dialog](images/bundle/setup.png)

You can install the agent without an install code, but it will be unable to register with the server. To add an install code after the install, either run the bundled installer again or use the __SetAmsServer.ps1__ script in `c:\program files\thycotic\powershell\arellia.agent`.

The __SetAmsServer.ps1__ script will ask for the server and a valid install code.

If older agents are used, the __Prevent Legacy Agent Registration (10.4 and older)__ option might be checked under ADMIN | Configuration and the Advanced tab, which prevents older agents without install code from registering.

If an agent was previously installed and never revoked, the endpoint will still have a valid certificate and a new agent can be installed with post-install registration.
