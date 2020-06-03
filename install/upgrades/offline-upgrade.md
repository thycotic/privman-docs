[title]: # (Offline Upgrades)
[tags]: # (new version)
[priority]: # (1702)
# Offline Upgrades

Follow these steps to perform an offline upgrade for Privilege Manager. This article is ONLY applicable when upgrading from versions 10.2 and higher.

1. Go to https://thycotic.force.com/support/s/download-onprem
1. Download the Privilege Manager Application Files (not the Installer .exe); this will download a .zip, for example Version_10_7_000000.zip
1. Extract the zip file.
1. From the unzipped folder, copy the contents of the nugetCache folder to this location on the web server: `C:\ProgramData\NugetCache`
1. On the web server, go to the TMS folder (default install locations include `C:\inetpub\wwwroot\TMS` or `C:\inetpub\wwwroot\SecretServer\TMS`)
1. Open the web.config in your favorite file editing tool, for example Notepad.
1. Find the following line:

   ```xml
   <add key="nuget:source:SolutionCentre" value="http://tmsnuget.thycotic.com/nuget/" />
   ```
1. Edit this line to change the path to `C:\ProgramData\NugetCache\`:

   ```xml
    <add key="nuget:source:SolutionCentre" value="C:\ProgramData\NugetCache\" />
   ```
1. Save the web.config
1. Recycle the TMS app pools.
1. Navigate to __ADMIN | More...__ and select __Add / Upgrade Privilege Manager Features__.
   This step will require windows authentication using an account that has local administrator permissions on the web server. The page should have a blue dialogue box stating:

   "You are viewing a local (cached) repository of product options.
   For an up-to-date list of products available, switch to the online repository"

   Also, the version numbers available should match the highest versions available in the C:\ProgramData\NugetCache\ folder on the web server.

>**Note**:
>Do NOT select the link to "...switch to the online repository", unless you want to revert the changes made above. Selecting this will edit the web.config back to the original SolutionCentre web path.

An upgrade or repair to the product may rewrite the web.config with default settings. Always double-check that the web.config has the correct SolutionCentre path whenever you perform a manual upgrade.

>**Note**: Thycotic recommends to create a back-up copy of the Privilege Manager web application folder after installation or upgrades.
