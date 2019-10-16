[title]: # (macOS Secure Token)
[tags]: # (local service accounts)
[priority]: # (1601)
# macOS Secure Token

Secure Token is a macOS High Sierra or later account attribute, that is required to be added to a user account before that account can be enabled for FileVault on an encrypted Apple File System (APFS) volume. To help make sure that at least one account has a Secure Token attribute associated with it, a Secure Token attribute is automatically added to the first account to log into the OS login window on a particular Mac.

The primary user created at the initial bootstrapping of the machine is always granted the initial Secure Token and then can grant further Secure Tokens. Once an account has a Secure Token associated with it, it can create other accounts which will in turn automatically be granted their own Secure Token.

Privilege Manager makes use of the local service account and stored (encrypted) password as part of the provisioning of a user. In order to support Secure Token during account creation and for password management, the agent service needs to use an account configured with a Secure Token to call the necessary command-line tools. The credential for the Secure Token User can be entered on the MacOS Agent Configuration page.

<!-- Not sure if the following paragraph is needed for customers. --->
The LocalSecurity plugin achieves results by running various macOS command-line tools. Commands that are concerned with getting information can typically be run as a normal user and do not require to be run as root. However, there are some commands that require root access and some that require admin credentials to be passed to them via parameters. Based on this, three classes of commands are being handled:

* Root Not Required
* Root Required
* Credentials Required

<!-- used as doc info source only - probably can be deleted at this point.
Agent Running as Service Account

If the agent service is refactored to run as a specific service account, the Root Required commands still need to be run as root. For those commands to be run, a privileged helper would be required and that presents the following problems:

Privileged Helpers require the same code signing certificate between the caller and the callee.
.NET binaries don’t support a plist that requires the necessary values for the SMPrivilegedExecutables key.
Standard Cocoa NSXPC* is not available on the .NET platform.

Since these are significant roadblocks, we would need to create a command-line tool that the agent calls that interfaces with the privileged helper. It would have to be able to take an arbitrary string of command data and pass it to the privileged helper. To prevent abuse, we’d need some way of validating the source of the command data. We could encrypt the data before sending it to the privileged helper and then decrypt it upon receiving. Failure to decrypt would obviously return a failure. Alternatively, we could perform message signing instead. Neither are tamper proof, but they might meet the minimum criteria for preventing arbitrary applications from using the privileged helper to escalate.

Creating a Service Account

We will need to create a managed account on macOS during product installation and ensure that it is enabled for SecureToken to perform the commands that require credentials. The agent service would then be configured to run as this user by adding the following key/value to its plist file (/Library/LaunchDaemons/com.thycotic.agent.plist):

<key>UserName</key>

<string>_privman | com.thycotic.privman | _acsagent</string>

The username may need to be more generic so that it doesn’t standout too much for the IBM brand of the product. A corresponding group would need to be created and the user added to it.

The following directories need the owner:group set (e.g. chown -R _privman:_privman):

/usr/local/thycotic/agent

/Library/Application Support/Thycotic/Agent – needed for access to read/write the .lock file

/var/log/thycotic – needed for writing to agent.log and agentutil.log

Ideally, the latter would have a child “agent” directory to separate it from other things that might get added later that might need another owner:group for discrete permissions.

All of these operations would need to be performed during the install/upgrade in a pre or post install phase.

This doesn’t address how we would go about randomizing and subsequently accessing the password necessary for the commands that need the _privman credentials.

Agent Running as Root

This mode of operation requires the least amount of change and requires the least amount of effort. No privileged helper is needed to run the Root Required commands. The service account for performing the Credentials Required commands would still be necessary. Consequently, those commands would need to be modified to properly retrieve and use the new credentials.

Just as with running with a service account, the credentials will need to be managed, randomized, etc. Both approaches require the use of sysadminctl and providing credentials as command-line parameters.
-->

## Agent Configuration

<!-- TODO: waiting for UI Implementation #148502 -->