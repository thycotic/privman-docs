[title]: # (macOS Specific)
[tags]: # (troubleshooting)
[priority]: # (1)
# MacOS Specific Troubleshooting

## Access to Directories

On Catalina based macOS systems, when .pkg installers are downloaded to a users home directory vs. a public folder, an error like the following example is triggered with a 256 response code:

`Error message: PrivManACS W: Unknown callback for event 3226790335 and filepath /Users/johndoe/Downloads/Microsoft_Outlook_16.32.19120802_Updater.pkg`

Catalina has a new security restriction that prevents daemons and applications that don’t have the full disk access entitlement from accessing files in certain directories in the users home directory. This includes __~/Downloads__, __~/Documents__, etc.

__~/Public__ is exempt, because it is public.

Versions prior to Catalina do not experience this restriction.

### Workaround via MDM Solution

If an MDM solution is in place, a TCC profile can be used to alleviate the problem. The below example can be used as a starting point. The example was specifically created for full disk access for a mobile configuration.

Either create a TCC profile based on this example for your environment or copy and paste the contents into a file and edit to meet your requirements.

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
            <string>com.thycotic.privilegemanager.thycoticacsvc.01BF42EA-574B-47A3-8B06-CBA3731973EE</string>
            <key>PayloadOrganization</key>
            <string>Thycotic Software, LLC</string>
            <key>PayloadType</key>
            <string>com.apple.TCC.configuration-profile-policy</string>
            <key>PayloadUUID</key>
            <string>01BF42EA-574B-47A3-8B06-CBA3731973EE</string>
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
                        <string>anchor apple generic and identifier "com.thycotic.ThycoticACS" and (certificate leaf[field.1.2.840.113635.100.6.1.9] /* exists */ or certificate 1[field.1.2.840.113635.100.6.2.6] /* exists */ and certificate leaf[field.1.2.840.113635.100.6.1.13] /* exists */ and certificate leaf[subject.OU] = UJDHBB2D6Q)</string>
                        <key>Comment</key>
                        <string>Allow SystemPolicyAllFiles control for Privilege Manager ThycoticACSvc</string>
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
    <string>Allows Privilege Manager to access all files on Catalina and higher</string>
    <key>PayloadDisplayName</key>
    <string>Privilege Manager ThycoticACSvc Profile</string>
    <key>PayloadIdentifier</key>
    <string>com.thycotic.privilegemanager.thycoticacsvc</string>
    <key>PayloadOrganization</key>
    <string>Thycotic Software, LLC</string>
    <key>PayloadRemovalDisallowed</key>
    <true/>
    <key>PayloadScope</key>
    <string>system</string>
    <key>PayloadType</key>
    <string>Configuration</string>
    <key>PayloadUUID</key>
    <string>01BF42EA-574B-47A3-8B06-CBA3731973EE</string>
    <key>PayloadVersion</key>
    <integer>1</integer>
</dict>
</plist>

```