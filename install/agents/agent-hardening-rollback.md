[title]: # (Hardening Rollback)
[tags]: # (endpoint,hardening)
[priority]: # (1621)
# Restore Default Agent Permissions

If you need to rollback agent hardening on your endpoints, follow these steps to restore the default agent permissions:

1. Import the following XML:

```xml
   <items>
<AgentPowershellScriptContract xmlns:adc="http://schemas.arellia.com/dc/" xmlns:arr="http://schemas.microsoft.com/2003/10/Serialization/Arrays" xmlns:mss="http://schemas.microsoft.com/2003/10/Serialization/" xmlns:dc="http://schemas.datacontract.org/2004/07/System" xmlns:adcpip="http://schemas.arellia.com/dc/Parameters/ItemPicker/" xmlns:adcp="http://schemas.arellia.com/dc/Parameters/" xmlns:adcpb="http://schemas.arellia.com/dc/Parameters/Basic/" xmlns:adcpm="http://schemas.arellia.com/dc/Parameters/Property/" xmlns:i="http://www.w3.org/2001/XMLSchema-instance" xmlns="http://schemas.arellia.com/dc/ClientItem/">
    <adc:Attributes>NoModify NoReplication NoDelete</adc:Attributes>
    <adc:Description>Local Security Clear Restrictive Service Security Powershell Script</adc:Description>
    <adc:FolderId>a7c39197-f7b8-478b-b7f7-ec574f71cf20</adc:FolderId>
    <adc:ItemId>e725443d-1065-4b40-8cea-5cff081030f2</adc:ItemId>
    <adc:Name>Local Security Clear Restrictive Service Security Script</adc:Name>
    <adc:ProductId>a7d32f79-5ac0-4a9c-a980-046752703ac6</adc:ProductId>
    <InputParameters>
        <adcp:Parameter>
            <adcp:DataType>http://schemas.microsoft.com/2003/10/Serialization/:ArrayOfguid</adcp:DataType>
            <adcp:DefaultValue i:nil="true" />
            <adcp:DisplayOrder>1</adcp:DisplayOrder>
            <adcp:Metadata>
                <adcp:MetadataValue mss:type="mss:ArrayOfguid" adcp:name="adcpip:RoleTypeIds" xmlns:i="http://www.w3.org/2001/XMLSchema-instance">
                    <arr:guid>192132a6-6c9a-4a29-8431-3688928d9c7a</arr:guid>
                </adcp:MetadataValue>
                <adcp:MetadataValue mss:type="mss:string" adcp:name="adcp:ControlType">ItemSelector</adcp:MetadataValue>
                <adcp:MetadataValue mss:type="mss:boolean" adcp:name="adcpip:CanSelectMultiple">true</adcp:MetadataValue>
            </adcp:Metadata>
            <adcp:Name>ServiceIds</adcp:Name>
            <adcp:Nullable>false</adcp:Nullable>
            <adcp:Prompt>Services</adcp:Prompt>
            <adcp:Visible>true</adcp:Visible>
        </adcp:Parameter>
        <adcp:Parameter>
            <adcp:DataType>System.Guid</adcp:DataType>
            <adcp:DefaultValue mss:type="mss:guid">a26f356f-67bf-42d9-9a2b-863a3f6570f5</adcp:DefaultValue>
            <adcp:DisplayOrder>2</adcp:DisplayOrder>
            <adcp:Metadata>
                <adcp:MetadataValue mss:type="mss:ArrayOfguid" adcp:name="adcpip:RoleTypeIds" xmlns:i="http://www.w3.org/2001/XMLSchema-instance">
                    <arr:guid>f8a1a9c4-ca0f-4bfb-ab80-8b66e4d88397</arr:guid>
                </adcp:MetadataValue>
                <adcp:MetadataValue mss:type="mss:string" adcp:name="adcp:ControlType">ItemSelector</adcp:MetadataValue>
            </adcp:Metadata>
            <adcp:Name>SecurityDescriptorId</adcp:Name>
            <adcp:Nullable>false</adcp:Nullable>
            <adcp:Prompt>Security Descriptor</adcp:Prompt>
            <adcp:Visible>false</adcp:Visible>
        </adcp:Parameter>
        <adcp:Parameter>
            <adcp:DataType>System.String</adcp:DataType>
            <adcp:DefaultValue i:nil="true" />
            <adcp:DisplayOrder>3</adcp:DisplayOrder>
            <adcp:Metadata>
                <adcp:MetadataValue mss:type="mss:guid" adcp:name="adcp:DynamicProviderId">be7fe5d0-7f6a-449a-8769-f87daf0b3fed</adcp:MetadataValue>
                <adcp:MetadataValue mss:type="mss:string" adcp:name="adcp:RelatedParameter">ServiceIds</adcp:MetadataValue>
                <adcp:MetadataValue mss:type="mss:boolean" adcp:name="adcp:RemoveRelatedParameter">true</adcp:MetadataValue>
            </adcp:Metadata>
            <adcp:Name>ServiceNames</adcp:Name>
            <adcp:Nullable>true</adcp:Nullable>
            <adcp:Visible>false</adcp:Visible>
        </adcp:Parameter>
        <adcp:Parameter>
            <adcp:DataType>System.String</adcp:DataType>
            <adcp:DefaultValue i:nil="true" />
            <adcp:DisplayOrder>4</adcp:DisplayOrder>
            <adcp:Metadata>
                <adcp:MetadataValue mss:type="mss:string" adcp:name="adcp:ControlType">TextBox</adcp:MetadataValue>
                <adcp:MetadataValue mss:type="mss:guid" adcp:name="adcp:DynamicProviderId">a96d3713-a83d-4374-9ed3-2f3ce1d4ee02</adcp:MetadataValue>
                <adcp:MetadataValue mss:type="mss:string" adcp:name="adcp:RelatedParameter">SecurityDescriptorId</adcp:MetadataValue>
                <adcp:MetadataValue mss:type="mss:boolean" adcp:name="adcp:RemoveRelatedParameter">true</adcp:MetadataValue>
            </adcp:Metadata>
            <adcp:Name>Sddl</adcp:Name>
            <adcp:Nullable>true</adcp:Nullable>
            <adcp:Visible>false</adcp:Visible>
        </adcp:Parameter>
    </InputParameters>
    <Script><![CDATA[Param(
	[string[]] $ServiceNames,
	[string] $Sddl
)
​
Add-Type -TypeDefinition @"
using System;
using System.Runtime.InteropServices;
using System.Security.AccessControl;
​
public class ServiceSecurity
{
   [DllImport("advapi32.dll", SetLastError=true)]
   public static extern bool SetServiceObjectSecurity(IntPtr hService, SecurityInfos secInfos, byte[] lpSecDesrBuf);
   [DllImport("advapi32.dll", EntryPoint="OpenSCManagerW", ExactSpelling=true, CharSet=CharSet.Unicode, SetLastError=true)]
   public static extern IntPtr OpenSCManager(string machineName, string databaseName, uint dwAccess);
   [DllImport("advapi32.dll", SetLastError=true, CharSet=CharSet.Auto)]
   public static extern IntPtr OpenService(IntPtr hSCManager, string lpServiceName, uint dwDesiredAccess);
   [DllImport("advapi32.dll", SetLastError=true)]
   [return: MarshalAs(UnmanagedType.Bool)]
   public static extern bool CloseServiceHandle(IntPtr hSCObject);
    
   public static void SetSecurityDescriptor(string serviceName, GenericSecurityDescriptor securityDescriptor)
   {
      uint WRITE_DAC = 0x00040000;
      IntPtr scHandle = OpenSCManager(null, null, WRITE_DAC);
​
      if (scHandle == IntPtr.Zero) { return; }
      
      IntPtr schService = OpenService(scHandle, serviceName, WRITE_DAC);
      if (schService == IntPtr.Zero) {
         CloseServiceHandle(scHandle);
         return;
      }
​
      try {
         var rawSD = new byte[securityDescriptor.BinaryLength];
         securityDescriptor.GetBinaryForm(rawSD, 0);
​
         var bSuccess = SetServiceObjectSecurity(schService, SecurityInfos.DiscretionaryAcl, rawSD);
         if (!bSuccess)
            Marshal.ThrowExceptionForHR(Marshal.GetHRForLastWin32Error());
      }
      finally {
         CloseServiceHandle(schService);
         CloseServiceHandle(scHandle);
      }
   }
}
"@
​
$RawSD = [Security.AccessControl.RawSecurityDescriptor]$Sddl
ForEach ($ServiceName in $ServiceNames) {
    [ServiceSecurity]::SetSecurityDescriptor($ServiceName, $RawSD)
}]]></Script>
</AgentPowershellScriptContract>
<RemoteScheduledClientCommandContract xmlns:adc="http://schemas.arellia.com/dc/" xmlns:arr="http://schemas.microsoft.com/2003/10/Serialization/Arrays" xmlns:mss="http://schemas.microsoft.com/2003/10/Serialization/" xmlns:dc="http://schemas.datacontract.org/2004/07/System" xmlns:d1p5="http://schemas.arellia.com/dc/Parameters/" xmlns:d1p6="http://schemas.arellia.com/dc/Resource/" xmlns:d1p7="http://schemas.arellia.com/dc/Task/" xmlns:i="http://www.w3.org/2001/XMLSchema-instance" xmlns="http://schemas.arellia.com/dc/ClientItem/">
    <adc:Attributes>NoReplication</adc:Attributes>
    <adc:Description>Sets the Security Descriptor back to Default on Thycotic services.</adc:Description>
    <adc:FolderId>37888218-c571-4356-ab82-81c1d1b1528f</adc:FolderId>
    <adc:ItemId>81fb5195-bcc1-4fe3-800c-4f0c7149fdf1</adc:ItemId>
    <adc:Name>Agent Service Clear Restrictions (Windows)</adc:Name>
    <adc:ProductId>a7d32f79-5ac0-4a9c-a980-046752703ac6</adc:ProductId>
    <ApplyToResourcesSettings>
        <d1p6:AllowedTargetRoleTypeId>493435f7-3b17-4c4c-b07f-c23e7ab7781f</d1p6:AllowedTargetRoleTypeId>
        <d1p6:RequiresScopingSecurity>false</d1p6:RequiresScopingSecurity>
        <d1p6:RestrictionCollectionId>d5385ec2-69b2-4506-9fb0-b8ea6efa97de</d1p6:RestrictionCollectionId>
        <d1p6:ScopingSecurityOperationId>00000000-0000-0000-0000-000000000000</d1p6:ScopingSecurityOperationId>
    </ApplyToResourcesSettings>
    <ClientCommandId>e725443d-1065-4b40-8cea-5cff081030f2</ClientCommandId>
    <DefaultResourceTargetIds>
        <arr:guid>eb5326c2-dfbe-4399-8c53-d980a673fd95</arr:guid>
    </DefaultResourceTargetIds>
    <DefaultTriggers xmlns:d2p1="http://schemas.arellia.com/dc/TaskScheduler/" i:nil="true" />
    <Enabled>false</Enabled>
    <InputParameterValues>
        <d1p5:ParameterValue>
            <d1p5:Name>ServiceIds</d1p5:Name>
            <d1p5:Value mss:type="mss:ArrayOfguid" xmlns:i="http://www.w3.org/2001/XMLSchema-instance">
                <arr:guid>5638834d-aecb-518f-b234-9a5dc149a37e</arr:guid>
                <arr:guid>675bb17e-d339-54a3-8d5e-ab5bd272b7e9</arr:guid>
            </d1p5:Value>
        </d1p5:ParameterValue>
    </InputParameterValues>
    <Settings>
        <d1p7:AllowDemandStart>true</d1p7:AllowDemandStart>
        <d1p7:DeleteExpiredTaskAfter>PT0S</d1p7:DeleteExpiredTaskAfter>
        <d1p7:DisallowStartIfOnBatteries>true</d1p7:DisallowStartIfOnBatteries>
        <d1p7:MultipleInstances i:nil="true" />
        <d1p7:Priority>Normal</d1p7:Priority>
        <d1p7:RestartCount>0</d1p7:RestartCount>
        <d1p7:StopIfGoingOnBatteries>true</d1p7:StopIfGoingOnBatteries>
    </Settings>
</RemoteScheduledClientCommandContract>
</items>
```
1. Navigate to __ADMIN | Policies__ and select the General tab.
1. Search for and disable the __Agent Service Start / Stop Control (Windows)__ policy.
1. Search for and enable the __Agent Service Clear Restrictions (Windows)__ policy.

   ![Clear Restrictions](images/agent-har/clear-restrict.png "Agent Service Clear Restrictions policy")
1. On the Targets tab specify the computers that need to be targeted by this policy.
1. On the Triggers tab specify when to run and/or what events will trigger the policy to run.
1. Click __Save__.


<!-- no go
1. Navigate to __ADMIN | More...__ and select __Folders__.
1. In the Policies folder tree open __General | Windows__.

   ![Rollback 1](images/agent-har/h-rollback-1.png "Policies Folders showing General | Windows node")
1. Click __Add New__.
1. From the __Template__ drop-down select __Local Security Scheduled Client Task__.
1. Name your policy _Restore Agent Security Permissions_.
1. As a command enter __Local Security Set Service Security Script__.
1. Click __Create__.

   ![Rollback 2](images/agent-har/h-rollback-2.png "Remote Schedule Client Command")
1. Click __Edit__.
1. Select the __Parameters__ tab.
1. For __Service__ add the __ArelliaAgent__ service.
1. For __Security Descriptor__ add the __Standard Service Security Descriptor__.
1. Click __Save__.

   ![Rollback 3](images/agent-har/h-rollback-3.png "ArelliaAgent Service and Security Descriptor")
1. Click __Create a Copy__.
1. Name the copy _Restore ACSAgent Security Permissions_.
1. Click __Create__.
1. Click __Edit__.
1. Select the __Parameters__ tab.
1. For __Service__ add the __ArelliaACScv__ service.

   ![Rollback 4](images/agent-har/h-rollback-3.png "ArelliaACSvc Service")
1. Click __Save__.

Add the Remote Scheduled Client Commands to a policy to have the agents pick up the rollback.
-->