[title]: # (Third-party Foreign Systems)
[tags]: # (integration)
[priority]: # (3)
# Third-Party Foreign Systems Integration

* [Setting up a Cylance Connection](set-up-cylance.md)
* [Setting up a Jamf Connection](set-up-jamf.md)
* [Setting up an SCCM Connection](set-up-sccm.md)
* [Setting up a ServiceNow Ticketing Connection](set-up-servicenow.md)
  * [ServiceNow Application](set-up-servicenow-app.md)
  * [Setting up a ServiceNow Webhook](set-up-servicenow-webhook.md)
* [Setting up the SMP Integration](set-up-smp.md)
* [Setting up an SMTP Server Connection](set-up-smtp.md)
* [Setting up a Syslog Connection](set-up-syslog.md)
* [Setting up a VirusTotal Connection](set-up-virustotal.md)

## Installing Foreign System Connectors

Foreign system connectors are not automatically installed on the Privilege Manager instances. These are the basic steps of installing a connector:

1. Open the Privilege Manager console.
1. Browse to `https://YourInstanceName/TMS/Setup/`.
1. On the __Currently Installed Products__ page, Click __Install/Upgrade Products__.
1. Select the connectors you wish to install.
1. Click __Install__. Accept any End User License Agreement if prompted and monitor the installation process for error conditions.

Privilege Manager cloud instances have connectors pre-installed and available for configuration without the need to run through the connector install.
