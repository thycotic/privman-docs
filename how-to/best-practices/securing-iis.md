[title]: # (Securing the IIS Server)
[tags]: # (database object)
[priority]: # (2)
# Securing the IIS Server

This is a list of items that IIS admin can implement to secure the IIS/Web server.

## Patches and Updates
  
Run Microsoft Baseline Security Analyzer on a regular interval to check for latest operating system and components updates.  
The latest updates and patches are applied for Windows, IIS server, and the .NET Framework. (These should be tested on development servers prior to deployment on the production servers.)  
Check the Microsoft Security Updates at https://docs.microsoft.com/en-us/security-updates/ on a regular interval for up to date Microsoft technical security notifications.

## Services

* Unnecessary Windows services are disabled.  
* Services are running with least-privileged accounts.  
* FTP, SMTP, and NNTP services are disabled if they are not required.  
* Telnet service is disabled.  
* ASP .NET state service is disabled and is not used by your applications.

## Protocols  

* WebDAV is disabled if not used by the application OR it is secured if it is required.  
* TCP/IP stack is hardened.  
* NetBIOS and SMB are disabled if not used (closes ports 137, 138, 139, and 445).

## Accounts

* Unused accounts are removed from the server.  
* Windows Guest account is disabled.  
* Administrator account is renamed and has a strong password.  
* IUSR_MACHINE account is disabled if it is not used by the application.  
* If your applications require anonymous access, a custom least-privileged anonymous account is created.  
  * The anonymous account does not have write access to Web content directories and cannot execute command-line tools.  
* ASP.NET process account is configured for least privilege. (This only applies if you are not using the default ASPNET account, which is a least-privileged account.)  
* Strong account and password policies are enforced for the server.  
* Remote logons are restricted. (The "Access this computer from the network" user-right is removed from the Everyone group.)  
* Null sessions (anonymous logons) are disabled.  
* No more than two accounts exist in the Administrators group.

## Files and Directories  

* Files and directories are contained on NTFS volumes.  
* Web site content is located on a non-system NTFS volume.  
* Log files are located on a non-system NTFS volume and not on the same volume where the Web site content resides.  
* The Everyone group is restricted (no access to `\Windows\system32` or Web directories).  
* Web site root directory has deny write ACE for anonymous Internet accounts.  
* Content directories have deny write ACE for anonymous Internet accounts.  
* Remote IIS administration application is removed.  
* Resource kit tools, utilities, and SDKs are removed.

## Shares

* All unnecessary shares are removed (including default administration shares).  
* Access to required shares is restricted (the Everyone group does not have access).  
* Administrative shares (C\$ and Admin\$) are removed if they are not required.

## Ports  

* Internet-facing interfaces are restricted to port 80 (and __443__ if SSL is used).  
* Intranet traffic is encrypted (for example, with SSL) or restricted.

## Registry
Remote registry access is restricted.  
SAM is secured (`HKLM\System\CurrentControlSet\Control\LSA\NoLMHash`).

## Auditing and Logging

* Failed logon attempts are audited.  
* IIS log files are relocated and secured.  
* Log files are configured with an appropriate size depending on the application security requirement.  
* Log files are regularly archived and analyzed.  
* Access to the Metabase.bin file is audited.  
* IIS is configured for W3C Extended log file format auditing.

## Sites and Virtual Directories

* Web sites are located on a non-system partition.  
* "Parent paths" setting is disabled.  
* Potentially dangerous virtual directories, including IISSamples, IISAdmin,
* IISHelp, and Scripts virtual directories, are removed.  
* MSADC virtual directory (RDS) is removed or secured.  
* Include directories do not have Read Web permission.  
* Virtual directories that allow anonymous access restrict Write and Execute Web permissions for the anonymous account.  
* There is script source access only on folders that support content authoring.  
* There is write access only on folders that support content authoring and these folder are configured for authentication (and SSL encryption, if required).  
* FrontPage Server Extensions (FPSE) are removed if not used. If they are used, they are updated and access to FPSE is restricted.

## Script Mappings

* Extensions not used by the application are mapped to 404.dll (.idq, .htw, .ida, .shtml, .shtm, .stm, idc, .htr, .printer).  
* Unnecessary ASP.NET file type extensions are mapped to "HttpForbiddenHandler" in Machine.config.

## ISAPI Filters

Unnecessary or unused ISAPI filters are removed from the server.

## IIS Metabase

* Access to the metabase is restricted by using NTFS permissions `%systemroot%\system32\inetsrv\metabase.bin`). 
* IIS banner information is restricted (IP address in content location disabled).

## Server Certificates

* Certificate date ranges are valid.  
* Certificates are used for their intended purpose (for example, the server certificate is not used for e-mail).  
* The certificate's public key is valid, all the way to a trusted root authority.  
* The certificate is SHA 256 or better.

## Machine.config

* Protected resources are mapped to HttpForbiddenHandler.  
* Unused HttpModules are removed.  
* Tracing is disabled `<trace enable="false"/>`  
* Debug compiles are turned off. `<compilation debug="false" explicit="true" defaultLanguage="vb">`

## Code Access Security

* Code access security is enabled on the server.  
* All permissions have been removed from the local intranet zone.  
* All permissions have been removed from the Internet zone.

## Other Check Points

* HTTP requests are filtered.  
* Remote administration of the server is secured and configured for encryption, low session time-outs, and account lockouts.

## Other Considerations

* Do use a dedicated machine as a Web server.  
* Do physically protect the Web server machine in a secure machine room.  
* Do configure a separate anonymous user account for each application, if you host multiple Web applications,  
* Do not install the IIS server on a domain controller.  
* Do not connect an IIS Server to the Internet until it is fully hardened.  
* Do not allow anyone to locally log on to the machine except for the administrator.
