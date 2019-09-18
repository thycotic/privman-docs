[title]: # (- Advanced Tab)
[tags]: # (user interface,console,overview)
[priority]: # (2108)
# Advanced Tab

The Advanced tab lets you configure 

* File Inventory Solutions such as
  * Collectors
* Privilege Manager Server
  * in General
  * Monitor
  * Proxy
  * Service Bus

## File Inventory Solution

Under the File Inventory Solution the file extensions used for inclusions and exclusions are specified. 

* ISO contents filters with default extensions of .exe, .cat, and .zip.
* MSI contents filters with default extensions of .exe, and .cat.
* Package contents filters with default extensions of .exe, .iso, .msi, .cat, .vhd, .vmdk, and .zip.
* VHD contents filters with default extensions of .exe, .cat, and .zip.
* ZIP contents filters with default extensions of .exe, .cat, . msi, and .zip.

When you click Edit at the bottom of the page, you can change any of the listed file extensions. 

![Collectors file extension filters](images/advanced/collectors.png)

## General System Settings

Under the Privilege Manager Server category, the first section is General settings.

![Privilege Manager General](images/pm/system.png)

### Allow Agent Certificate Mismatch

This is a checkbox that when selected allows agents to communicate with the server even if there is a certificate mismatch.

### Maximum Application Event Count

This settings specifies the Maximum number of application action events that will be kept in the database. The default setting is 1,000,000.

### Command Timeout

This settings specifies the SQL command timeout. The default is 180 Seconds.

### Encryption Provider

This setting specified the Encryption Provider used to encrypt sensitive data.

### Inactivity Timeout

This settings specifies the maximum allowed time for inactivity when logged into the Privilege Manager console. The default is set to 30 Minutes.

### Max Time Skew

This setting specifies the maximum time difference (in minutes) to allow client system clocks to be out of sync with the server.

### Prevent Legacy Agent Registration (10.4 and older)

Enabling this setting prevents older agents (prior to 10.5) from registering, allowing only agents with valid agent Install Codes. Only enable this option if you are certain your managed computers have all been upgraded to 10.5 or newer agents.

### Save Performance Counters

If this setting is selected, the performance counter data will be recorded in the database.

### Session Timeout

This setting specifies the maximum time in __minutes__ for a login session to be active without having to negotiate another token with the auth provider. The default is set to 720 Minutes (12 Hours).

### System Secret Vault

This link lets you configure the foreign system used to store secrets.

### Validate Agent Event Signatures

Enabling this setting will verify the signature contained within agent events that are sent to the server. Any events with invalid signatures are discarded.

## Monitor Settings

Under the Privilege Manager Server category, the second section is Monitor settings. The Monitor setting is designed to monitor the Worker Role to ensure it is healthy and active. When enabled, the process checks the health at each Ping Interval and waits until the Timeout value before considering it unhealthy.

![Privilege Manager Monitor](images/pm/monitor.png)

### Base Local Address

This setting specifies the base URL of the Monitor process.

### Monitor Worker Role

When this setting is enabled the health of the monitor process will be polled.

### Ping Interval

Specifies how often the server will attempt to contact the Monitor process to query its health. The default is set to 15 Seconds.

### Timeout

Specifies how long the server process will wait to hear back from a ping request to the Monitor process. The default is set to 30 Seconds.

## Proxy Settings

Under the Privilege Manager Server category, the third section is Proxy settings.

![Privilege Manager Proxy](images/pm/proxy.png)

### Proxy Server

This setting specifies the name or IP address of the proxy server.

### Proxy Server Credential

This link lets you configure the credential used to authenticate with the proxy server.

### Port

This setting specifies the port used for communications to the proxy server.

### Use Proxy Server

If set, communications will be done via the proxy server specified.

## ServiceBus Settings

Under the Privilege Manager Server category, the fourth section is ServiceBus settings.

![Privilege Manager ServiceBus](images/pm/servicebus.png)

### Connectivity Mode

This setting specifies the connectivity mode for Service Bus. The default is HTTPS, which is also recommended.
