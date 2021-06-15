[title]: # (Moving Privilege Manager)
[tags]: # (migration,installation)
[priority]: # (2)

# Migrating the Privilege Manager Server

If you are moving/migrating Privilege Manager to a new machine and have installed IIS and .NET Framework as described in the Installation Guide on the new machine, you do not need to run the installer, simply follow the steps below:

<!-- Not sure this is needed for Privman only installs:

If you use the "Force HTTPS/SSL" option, disable it by clicking Configuration from the Administration menu, and then click the Security tab, and Edit. If you are also moving the SQL Server database, be sure to create a new backup of the database, as this setting is written to it. You can re-enable the "Force HTTPS/SSL" option after you set up and install an SSL certificate on the new machine.


If you have configured encryption of your key using DPAPI, you will also need to turn this off before continuing with step 3. To do so, click Configuration from the Administration menu, then click the Security tab. Click Decrypt Key to not Use DPAPI and enter your Privilege Manager account password.
-->

1. Copy the folder that holds your Privilege Manager instance to the new computer.
1. Shut down the old web site and recycle its application pool as it is running background threads which are accessing the database.
1. Set up the new folder in Internet Information Server (IIS) as a virtual directory/application under the Default Web Site or as a separate Website (refer to the Advanced Installation section of the Installation Guide for detailed instructions).
1. Browse to your TMS URL database connection page e.g. `https://<YOUR_URL_INSTANCE>/TMS/setup/database/connectdatabase` (for Arellia this URL would be slightly different e.g. `https://<YOUR_URL_INSTANCE>/ams/setup/database/connectdatabase`) and you will see a page to enter your database connection details.

   <!-- 1. When you browse to Privilege Manager on the new machine it will usually state that it is a secondary node. This is because the database still knows about the previous server. If the old machine was a primary node, then follow these steps to change the new machine to being the primary node:
   1. On the server you will make this the primary node, navigate to Privilege Manager locally.
   1. Log in as an administrator, and click Server Nodes from the Administration menu.
   1. Click the Make Current Node Primary button.
   -->
1. Activate the licenses for the new server by going to the Licenses page.
1. If you are using certs, remember to set them on your new IIS, then browse to Privilege Manager over HTTPS and re-enable force HTTPS if this was set on the original machine.
1. Re-enable DPAPI if this was disabled in the earlier step.

>**Note**: If you're migrating the Privilege Manager web application from Windows Server 2008 to 2012 or newer AND your Privilege Manager is below version 8.5, make sure that:
>
> * .Net extensions 3.5 and ASP.Net 3.5 when adding the IIS role on the new server.
> * Change the Privilege Manager Application Pool to 2.0 and recycle the application pool after running the installer.

## Steps to Setup Secondary Node with both SS & PrivMan

If you are migrating a combined install environment, also perform these steps:

1. Check web-auth.config and web-cookie.config (in Secret Server web folder) to make sure forceSSL = 'false'.
1. Confirm app pool account and IIS settings (confirm if SS and TMS are virtual directories, confirm IIS auth settings).
1. Disable DPAPI.
1. Disable Force SSL.
1. Decrypt connectionStrings.config on primary web server:

   `C:\Windows\Microsoft.NET\Framework64\v4.0.30319\aspnet_regiis.exe -pd "connectionStrings" -app "/Tms"`
1. Copy files to secondary.
1. Download current installer to secondary server.
1. Run installer to __confirm and fix pre-requisites only__. __DO NOT install the application__ with the installer.
1. Make sure Secret Server and TMS web folders from primary are in `C:\inetpub\wwwroot` (or a similar location).
1. Create 4 app pools: SecretServer, TMS, TMSAgent, and TMSWorker (same as set for primary node).
1. Assign service account to all 4 app pools (same as set for primary node).
1. If the Secret Server and TMS directories do not appear in IIS Manager, add the virual directories (same as set for primary).
1. Convert to Applications

   1. Right-click on __Secret Server > Convert to Application__, make sure SecretServer app pool is assigned.
   1. Right-click on __TMS > Convert to Application__, make sure TMS app pool is used.
   1. Under TMS, right-click on __Agent > Convert to Application__, make sure TMSAgent app pool is used.
   1. Under TMS, right-click on __ServiceBus > Convert to Application__, make sure TMSWorker app pool is used.
   1. Under TMS, right-click on __Services > Convert to Application__, make sure TMS app pool is used.
   1. Under TMS, right-click on __Setup > Convert to Application__, make sure TMS app pool is used.
   1. Under TMS, right-click on __Worker > Convert to Application__, make sure TMSWorker app pool is used.
1. Run the ASP.NET IIS Registration Tool:

   1. Change the directory to your .NET framework installation directory using the "cd" command (i.e.: `C:\Windows\Microsoft.NET\Framework\v4.0.30319` or `C:\Windows\Microsoft.NET\Framework64\v4.0.30319`).
   1. Type in `.\aspnet_regiis -ga <domain name>\<user name>` and press enter.
1. Assign folder permissions:

   1. Give your service account "modify" access to `C:\Windows\TEMP`.
   1. Give your service account "modify" access to the Secret Server web folder.
   1. Give your service account "modify" access to the TMS web folder.
1. Set IIS authentications (set to same as primary, depending on IWA and other settings), typical example:

   * Secret Server (Anonymous & Forms, except winauthwebservices = Forms & Windows; see TMS notes)
1. Install certfification on new server, if not already done.
1. Give the 3 TMS App Pools read access on the PrivateKey of the cert.

   1. MMC snap-in > Certificates.
   1. Find the certificate (most like in personal store).
   1. Right-click > All Tasks > Manage PrivateKey.
   1. Choose local computer name from location and format is iis apppool\tms, iis apppool\tmsagent, iis apppool\tmsworker.
1. Login in to Secret Server.
1. Activate licenses.
1. Re-enabled Force SSL.
1. Re-enabled DPAPI on all web nodes.
1. Re-encrypt connectionStrings.config on all web nodes:

   C`:\Windows\Microsoft.NET\Framework64\v4.0.30319\aspnet_regiis.exe -pe "connectionStrings" -app "/Tms"`

