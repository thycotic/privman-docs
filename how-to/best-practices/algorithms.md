[title]: # (Security Algorithms)
[tags]: # (file hashes)
[priority]: # (2)

# Security Algorithms

Privilege Manager v11.1 introduced configurable security algorithms.

Configuration of security algorithms is managed via __Admin | Configuration | Advanced__ under the Agent section. Refer to [Advanced Tab](../../admin/config/advanced).

ThycoticCentrify recommends that all customers update to SHA256 at this point.

## Server-Targeted Settings

The following settings are targeted at the Privilege Manager server.

### Allowed agent event signature algorithms

This setting specifies what signature algorithms the server accepts when processing events from the agent. The new minimum standard for agents v11.1 events is XML RSA/SHA256. XML RSA/SHA1 is considered legacy support for older agent version only.

By default in v11.1 and up XML RSA/SHA256 and SHA1 are configured. Once your server only communicates with the latest agent version and all your policies/filters have been updated, SHA1 can be removed from the configuration.

### Client item signature algorithms

This is the list of one or more signature algorithms the server will use when signing client items.

* __Legacy Value__: XML RSA/SHA1
* __Default__: Both XML RSA/SHA1 and XML RSA/SHA256.

## Allowed client item signature algorithms

This setting specifies the signature algorithm(s) on tokens the server should accept for agent service calls.  

## Agent-Targeted Settings

These are settings that are targeted at agents, and will be part of agent configuration items. If the settings are not specified in the agent configuration contract XML, then the global setting will be sent to the agent.

### Agent Event Signature Algorithm

This is the signature algorithm agents are instructed to use when signing XML events.

* __Legacy/unspecified__: The legacy value is XML RSA/SHA1. Agents should continue using this if not specified in their configuration.
* __Default__: XML RSA/SHA256

### Inventory Hash Algorithms

These are the hash algorithms that agents should use when reporting inventory for resources.  

>**Note**: The agent should always report as many hashes as possible from the configured set. Legacy hashes don’t do any harm except maybe take up a bit of space.

* __Legacy__: The legacy values are mixed, some resources (like Folders) were using MD5, most files and other resources used SHA1.
* __Unset__: If the agent doesn’t have a configuration value for this, it reports all hashes it can from the set of (MD5, SHA1, SHA256, Authenticode, Authenticode 2).  
* __Default__: MD5, SHA1, SHA256, Authenticode, and Authenticode2.

>**Note**: Authenticode is a Windows technology for signing executables, it essentially contains the hash of the raw executable before signing. For non-Windows OSes and non-Executable resources, this hash is ignored.
