[title]: # (TLS Versions)
[tags]: # (help, service bus)
[priority]: # (2)

# Supporting Multiple TLS Versions

 Privilege Manager on-premise does not work with Azure Service Bus if the web server is set to use only TLS 1.2 and needs TLS 1.1 enabled to function.

To support a TLS version mismatch between Privilege Manager and the Azure Service Bus the web.config files for the Service Bus and Privilege Manager need to be edited as follows:

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
