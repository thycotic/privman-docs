[title]: # (Using MDM Profiles)
[tags]: # (macOS,agents)
[priority]: # (6)

# Using an MDM Profile for your Agent

If you utilize an MDM tool like JAMF, you can create configuration profiles to make management of the agent more silent on your macOS Catalina and Big Sur deployments.

You will need two different configuration profiles for each version of the agent (or two different payloads within the same profile):

* a KEXT or SYSEX Allow Profile
* a PPPC profile that gives Full Disk Access to ThycoticACSvc (KEXT) or com.thycotic.acsd (SYSEX). Refer to [macOS File/Folder Access](../../platforms/macOS/tcc-access.md)

## SYSEX

### SYSEX Allow Info

You can create a SYSEX Allow profile for ThycoticManagementAgent-10.8.nnnn.pkg and above using your MDM's profile creator and the following information:

* Team Identifier: UJDHBB2D6Q
* Allowed System Extensions: com.thycotic.acsd

## SYSEX PPPC Profile Info

1. Install the agent on a test endpoint.
1. Use Jamf's **PPPC Utility** or another method to create a profile that gives Full Disk Access to the Privilege Manager Security system extension (**com.thycotic.acsd.systemextension**) found under `Macintosh HD/Library/SystemExtensions`.

   Alternatively, make a custom configuration profile using the XML below:

```xml
<?xml version="1.0" encoding="UTF-8"?>
<!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd">
<plist version="1.0">
<dict>
<key>PayloadContent</key>
<array>
<dict>
<key>PayloadDescription</key>
<string>Allows Privilege Manager SYSEX to access all files on Catalina and higher</string>
<key>PayloadDisplayName</key>
<string>Privilege Manager Security</string>
<key>PayloadEnabled</key>
<true/>
<key>PayloadIdentifier</key>
<string>F34A5382-C24E-42D9-970E-4D6C0A03A229</string>
<key>PayloadOrganization</key>
<string>Thycotic</string>
<key>PayloadType</key>
<string>com.apple.TCC.configuration-profile-policy</string>
<key>PayloadUUID</key>
<string>41A7F168-58C5-4F98-BC37-5E762CF79595</string>
<key>PayloadVersion</key>
<integer>1</integer>
<key>Services</key>
<dict>
<key>SystemPolicyAllFiles</key>
<array>
<dict>
<key>Allowed</key>
<integer>1</integer>
<key>CodeRequirement</key>
<string>anchor apple generic and identifier "com.thycotic.acsd" and (certificate leaf[field.1.2.840.113635.100.6.1.9] /* exists */ or certificate 1[field.1.2.840.113635.100.6.2.6] /* exists */ and certificate leaf[field.1.2.840.113635.100.6.1.13] /* exists */ and certificate leaf[subject.OU] = UJDHBB2D6Q)</string>
<key>Identifier</key>
<string>com.thycotic.acsd</string>
<key>IdentifierType</key>
<string>bundleID</string>
<key>StaticCode</key>
<integer>0</integer>
</dict>
</array>
</dict>
</dict>
</array>
<key>PayloadDescription</key>
<string></string>
<key>PayloadDisplayName</key>
<string>Privilege Manager Security SYSEX PPPC FDA</string>
<key>PayloadEnabled</key>
<true/>
<key>PayloadIdentifier</key>
<string>749AFA6B-3B75-47CF-9A5B-89E909B785FD</string>
<key>PayloadOrganization</key>
<string>Thycotic LTD</string>
<key>PayloadRemovalDisallowed</key>
<true/>
<key>PayloadScope</key>
<string>System</string>
<key>PayloadType</key>
<string>Configuration</string>
<key>PayloadUUID</key>
<string>749AFA6B-3B75-47CF-9A5B-89E909B785FD</string>
<key>PayloadVersion</key>
<integer>1</integer>
</dict>
</plist>
```

## KEXT

### KEXT Allow Info

You can create a KEXT Allow profile for ThycoticManagementAgent-10.8.nn.pkg and below using your MDM's profile creator and the following information:

* Team ID: UJDHBB2D6Q
* Kernel Extension Bundle ID: com.thycotic.ThycoticACS

### KEXT PPPC Profile Info

1. Install the agent on a test endpoint.
1. Use Jamf's [PPPC Utility](https://github.com/jamf/PPPC-Utility) (free, no Jamf subscription needed) or another method to create a profile that gives Full Disk Access to the ThycoticACSvc daemon found under `Macintosh HD/Library/Extensions/ThycoticACS.kext/Contents/MacOS/ThycoticACSvc`

   Alternatively, make a configuration profile with the XML below:

```xml
<?xml version="1.0" encoding="UTF-8"?>
<!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd">
<plist version="1.0">
<dict>
<key>PayloadContent</key>
<array>
<dict>
<key>PayloadDescription</key>
<string>Allows Privilege Manager to access all files on Catalina and higher</string>
<key>PayloadDisplayName</key>
<string>Privilege Manager ThycoticACSvc Profile</string>
<key>PayloadIdentifier</key>
<string>com.thycotic.privilegemanager.thycoticacsvc</string>
<key>PayloadOrganization</key>
<string>Thycotic Software, LLC</string>
<key>PayloadType</key>
<string>com.apple.TCC.configuration-profile-policy</string>
<key>PayloadUUID</key>
<string>A63BED50-BCDB-4F17-824A-54A897DDF4FF</string>
<key>PayloadVersion</key>
<integer>1</integer>
<key>Services</key>
<dict>
<key>SystemPolicyAllFiles</key>
<array>
<dict>
<key>Allowed</key>
<true/>
<key>CodeRequirement</key>
<string>anchor apple generic and identifier "com.thycotic.ThycoticACS" and (certificate leaf[field.1.2.840.113635.100.6.1.9] /* exists */ or certificate 1[field.1.2.840.113635.100.6.2.6] /* exists */ and certificate
leaf[field.1.2.840.113635.100.6.1.13] /* exists */ and certificate leaf[subject.OU] = UJDHBB2D6Q)</string>
<key>Comment</key>
<string></string>
<key>Identifier</key>
<string>com.thycotic.ThycoticACS</string>
<key>IdentifierType</key>
<string>bundleID</string>
</dict>
</array>
</dict>
</dict>
</array>
<key>PayloadDescription</key>
<string>Allows Privilege Manager KEXT to access all files on Catalina</string>
<key>PayloadDisplayName</key>
<string>Privilege Manager ThycoticACSvc Profile</string>
<key>PayloadIdentifier</key>
<string>com.thycotic.privilegemanager.thycoticacsvc</string>
<key>PayloadOrganization</key>
<string>Thycotic Software, LLC</string>
<key>PayloadScope</key>
<string>System</string>
<key>PayloadType</key>
<string>Configuration</string>
<key>PayloadUUID</key>
<string>40A305B8-0558-4FA4-8B52-894727EFBD3D</string>
<key>PayloadVersion</key>
<integer>1</integer>
</dict>
</plist>
```
