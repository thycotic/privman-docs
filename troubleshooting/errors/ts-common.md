[title]: # (Common Errors)
[tags]: # (troubleshooting)
[priority]: # (2)
# Common Errors

## Access Denied

Error: "Access Denied. You do not have permission to view this directory or page using the credentials that you supplied."

To Resolve:

After logging in to Privilege Manager 10.3 with a user account that has Privilege Manager Administrator Role rights, if you experience this error, verify if SSL 3.0 and/or TLS 1.0 have been disabled.
If those protocols have been disabled on the server, you'll need to replace `C:\inetpub\wwwroot\Tms\bin\Thycotic.Owin.Security.dll` with `http://tmsnuget.thycotic.com/scripts/Thycotic.Owin.Security.dll`

Recycle the TMS Application Pools in IIS and attempt to access Privilege Manager again.

## Server Error in...

Error: "Server Error in '/' Application. Runtime Error"

Your Secret Server instance doesn't have the correct URL pointing at Privilege Manager.

To Resolve:

Go to your Secret Server instance (Tools | Secret Server). Then Admin | Configuration.
Verify that your TMS Installation URL is set to ~/../TMS. 

## SSL Connectivity or Certificate Issues

Error: SSL Connectivity or Certificate Issues?

### Trusting an SSL Certificate on a Client Machine (KB)

When a self-signed certificate is installed on a server for the Secret Server website, client computer browsers will generally give security warnings for that web site. This is because for public websites, only certificates issued by trusted authorities can be trusted as valid certificates. For certificates that will only be used within a company or domain, self-signed certificates the security warnings can generally be ignored.

However, the security warnings can also interfere with the use of the Secret Server Launcher and Web Password Filler. To resolve, the certificate can be installed on the client machine either through Internet Explorer or Certificates snap-in.

The following steps can be used to trust the certificate:

1. Make sure that the host to which the certificate is issued is the same as the host name for your Secret Server website.

   * Open Internet Explorer and navigate to Secret Server
   * Click Continue to this website if you are prompted
   * Click the Certificate Error icon next to the navigation bar and then click View certificate. The value next to Issued to should match the host name for your website. For example, if your website is `https://www.mydomain.local/SecretServer`, it should say "Issued to: www.mydomain.local". If these fields do not match, the client will not be able to fully trust the certificate.
1. Obtain a copy of the certificate file and transfer it to the client computer.

   * On the server that Secret Server is installed on, find Run from the start menu or screen and type in mmc, then hit Enter.
   * From the File menu, select Add/Remove Snap-in.
   * Select the Certificates snap-in, then click the right arrow button to add it.
   * In the window that appears, select Computer Account, then Local Computer, and then click Finish.
   * You should now see the Certificates (Local Computer) node. Expand the Personal folder and then the Certificates folder under it.
   * Right-click the certificate that Secret Server uses, then click All tasks and select Export.
   * Keep clicking Next to accept defaults in the wizard. Enter a filename, and then click Finish. The certificate has now been exported.
   * Copy the certificate from your server and transfer it to your client computer.
   |**Note**:
   |If you have Firefox, the certificate can be saved to your client computer by viewing and exporting it after navigating to the website.
1. Install the certificate on the client computer.
   * On the client computer, find Run from the start menu or screen and type in mmc, then hit Enter.
   * From the File menu, select Add/Remove Snap-in.
   * Select the Certificates snap-in, then click the right arrow button to add it.
   * In the window that appears, select My user account, and then click Finish.
   * Expand the Trusted Root Certification Authorities folder, then right-click the Certificates folder, and select All Tasks | Import.
   * Click Next and Yes to accept default settings for all steps of the wizard.
   * When prompted for the certificate file, select the file you saved in the previous step (2).

>**Note**:
>You may need to reopen Internet Explorer and browse to Secret Server once more to see the change reflected on the client machine.

### Granting Permissions on New SSL Certificate for Privilege Manager (KB)

If you change your certificate or if it is automatically renewed, you may need to grant permissions on your new SSL certificate to the service account that the TMS app pools run under.  TMS accesses the SSL certificate to sign all of the policies that Privilege Manager sends out to agents, adding an extra security layer to your environment.  

Messages you may see include: 

* https: does not render
* Navigating to Https://[ServerName]/TMS/PrivilegeManager loads a blank screen  
* Agents stop receiving configuration information from the Privilege Manager Web Server,
* Http : TMS requires an https (SSL) / secure connection

For the fastest resolution to Permissions issues, you can run a Powershell script:

* Navigate to your TMS Website on your Privilege Manager web server (Usually located in `c:\inetpub\wwwroot\` ), then navigate to `Tms\App_Data\Tools\SSLHelper.ps1` on your Privilege Manager web server, right-click this and select Run with Powershell to execute.

#### To grant permissions manually, follow these steps

1. Using MMC on your Privilege Manager web server, open the certificates snap-in (File|"Add/Remove Snap-in..." | Certificates | click Add), then select Computer account to manage the local computer. Click Next, then Finish and OK.
1. Double click Certificates (Local Computer) and locate the certificate that your TMS site is using (it will most likely be under Personal|Certificates unless you specified a different location*)
1. Right click on the certificate and select All Tasks | Manage Private Keys

#### Grant Read Access to the account(s) that TMS is running under

If this is a user account then you may adjust permissions to the user account. To check, go to your app pool in IIS, right-click the IIS app pool | Advanced Settings... | "Identity" row: if your app pool "identity" is listed as something OTHER THAN "ApplicationPoolIdentity" in IIS, i.e. "THYCOTIC |ServiceAccount", then your app pool is using a user account.

If this IS the Application Pool Identity (i.e. not a user account) you will need to adjust permissions to three app pools: "IIS AppPool\TMS", "IIS AppPool\TMSWorker" and  "IIS AppPool\TMSAgent." Note that names of app pools may vary depending on your environment.
  
Recycle your TMS, TMSAgent, and TMSWorker app pools in IIS.

>**Note**:
>If you are unsure which certificate matches the one you are using in IIS, follow these steps to ensure your certificate thumbprints match:

In IIS on your Privilege Manager web server, navigate to the site you are using to run Privilege Manager
Right-click on this site, click Bindings. Choose the https port you need to update and select Edit. View the SSL Certificate this is attached to.

Next, choose the Details tab and scroll down to find the certificate's Thumbprint. copy the list of numbers and letters that make up your certificate's thumbprint (a sha256 hash).

Return to your certificates in MMC (step 2 above). Right-click Certificates (Local Computer) and select Find Certificates...

In the Contains box, paste your Thumbprint sha256 hash and select sha256 from the Look in Field drop down. Click Find Now. This will return the certificate name that your Privilege Manager Binding is currently linked to.

## Tasks Stuck at Ready 

Error: Are your tasks sitting at "Ready" for extended periods of time? 

To Resolve:
 
1. Navigate to Admin | Configuration | Advanced and make sure the URL for the "Monitor Worker Role" are accurate for the bindings (Check the hostname in the Base local address and the Port).
1. Open IIS Manager, check to make sure the app pools have Read Access to the certificate that you’ve assigned to that binding via MMC Certificates plug-in. More instructions on how to do this in our Granting Permissions on New SSL Certificate for Privilege Manager KB, posted here.
1. Manually recycle the TMS and TMS Worker app pools.

## CPU Issue

Error: CPU overworked in your Agent or 'Unexpected failure in ACS Agent background'

Your agent may be configured incorrectly.

To Resolve:

1. In Privilege Manager navigate to Admin | Agents. 
1. Under the Windows tab, verify that your "Send Application events every" and "Refresh Client item cache every" settings are both set to 0.
1. Save changes, refresh your client item cache, enforce the update on your endpoint machine (Follow the update Powershell script instructions listed under  "How do I Update Specific Agents Immediately?" above).

## System Critical Error

Error:  'System Critical Error - execute/PolicyDetailComponent' in Firefox

To Resolve:

Open Privilege Manager in a different browser, such as Chrome or Internet Explorer 11.
If you prefer Firefox as your web browser, download this zip file: `http://tmsnuget.thycotic.com/scripts/firefox.fix.zip`
Unzip these files, then copy and paste into `C:\inetpub\wwwroot\Tms\Spa\PrivilegeManager\` on your Privilege Manager Server.

Refresh your Firefox browser.
