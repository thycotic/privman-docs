[title]: # (TLS Versions)
[tags]: # (help, service bus)
[priority]: # (2)

# Supporting Multiple TLS Versions

Privilege Manager on-premise does not work with Azure Service Bus if the web server is set to use only TLS 1.2.

For customers that want to restrict connections on their web server to TLS 1.2, need to make modifications to  C:\inetpub\wwwroot\Tms\ServiceBus\web.config and C:\inetpub\wwwroot\Tms\Worker\web.config. They also must have .NET Framework 4.6 or newer installed and modify the <system.web> section as follows:

1. Open `C:\inetpub\wwwroot\Tms\ServiceBus\web.config`.
1. Change the <system.web> section to:

   ```txt
   <system.web>
    <httpRuntime targetFramework="4.6"/>
     <authorization>
      <allow users="?"/>
     </authorization>

    <authentication mode="Windows"/>
   </system.web>
   ```
   
1. Save the file.
1. Open `C:\inetpub\wwwroot\Tms\Worker\web.config`.
1. Change the <system.web> section to:

   ```txt
   <system.web>
    <httpRuntime targetFramework="4.6"/>
     <authorization>
      <allow users="?"/>
     </authorization>

    <authentication mode="Windows"/>
   </system.web>
   ```

1. Save the file.
