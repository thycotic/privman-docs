[title]: # (Offline Upgrades)
[tags]: # (new version)
[priority]: # (1651)
# Offline Upgrades

Follow these steps to perform an offline upgrade for Privilege Manager. This article is ONLY applicable when upgrading from versions 10.2 and higher.

>**Note**: Offline upgrades on __multiple__ servers will need to be done manually.

1. Download the latest version for the Privilege Manager Offline Upgrade from [Software Downloads](../sw-downloads.md).
1. Extract the zip file.
1. From the unzipped folder, copy the contents of the nugetCache folder to this location on the web server: `C:\ProgramData\NugetCache\`
1. Navigate to the TMS web folder (`C:\inetpub\wwwroot\TMS\`), right-click and open with, e.g. __Notepad > Run as Administrator__ the __web.config__ file.
   1. Update the "value" field of this item `<add key="nuget:source:SolutionCentre" value="http://tmsnuget.thycotic.com/nuget/" />` to `C:\ProgramData\NugetCache\`, such as

      ```xml
      <add key="nuget:source:SolutionCentre" value="C:\ProgramData\NugetCache\" />
      ```
   1. Save the __web.config__ file.
   1. Recycle the TMS app pools.
1. Navigate to `https://<webserver>/TMS/Setup/ProductOptions/ShowProducts`. This step will require windows authentication using an account that has local administrator permissions on the web server.
1. You should see new products available in the products list. Click the __Install/Upgrade Products__ button.
1. Select the products you wish to upgrade or install, and follow the steps to finish the installation. If one of the products fails to install, please repeat these last two steps. You may encounter an issue with an error of "Version Store out of Memory" - this is transient and re-starting the upgrade will fix it. If you encounter any additional errors, please contact Thycotic Technical Support for assistance.

>**Note**: An upgrade or repair to the product may rewrite the web.config with default settings. Always double-check that the web.config has the correct SolutionCentre path whenever you perform a manual upgrade. Also, the version numbers available should match the highest versions available in the C:\ProgramData\NugetCache\ folder on the web server.
>
>Thycotic recommends to create a back-up copy of the Privilege Manager web application folder after installation or upgrades.
