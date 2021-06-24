[title]: # (Using MDM Profiles)
[tags]: # (macOS,agents)
[priority]: # (6)

# Using MDM Profiles for your Agent

If you utilize an MDM solution, you can create configuration profiles to make management of the agent silent on macOS deployments. We recommend deploying the relevant SYSEX or KEXT profiles prior to the agent deployment.

It is recommended to use the System Extension version, as Apple has deprecated the use of Kernel Extensions. Refer to [Software Downloads/macOS Endpoints](../../install/sw-downloads.md)

## System Extension (SYSEX)

### I. System Extension Allow Payload

Inside your MDM create a System Extension Allow profile based on the below information:

* Team Identifier: UJDHBB2D6Q
* Allowed System Extensions: com.thycotic.acsd

### II. SYSEX Privacy Preferences Policy Control (PPPC) Full Disk Access Payload

Inside your MDM create a PPPC profile based on below:

* Identifier: com.thycotic.acsd
* Identifier Type: Bundle ID
* Code Requirement:

```text
anchor apple generic and identifier "com.thycotic.acsd" and (certificate leaf[field.1.2.840.113635.100.6.1.9] /* exists */ or certificate 1[field.1.2.840.113635.100.6.2.6] /* exists */ and certificate leaf[field.1.2.840.113635.100.6.1.13] /* exists */ and certificate leaf[subject.OU] = UJDHBB2D6Q)
```

### III. (PPPC) Allow Notifications Payload

Refer to: [Manage Privilege Manager Notifications on macOS](../../ui/alert/macOS-notify-mgtm.md)

### IV. (PPPC) Allow AppleEvents and Accessibility Payload

Refer to the bottom of the page: [macOS Approval Process](../../computer-groups/macOS/examples/approval.md)

## Kernel Extension (KEXT)

Apple has deprecated the use of Kernel Extensions. The KEXT version is still available but macOS version dependant. Refer to [Software Downloads: macOS Endpoints](../../install/sw-downloads.md#macos_endpoints)

### I.  Kernel Extension Allow Payload

Inside your MDM create a Kernel Extension Allow profile based on the below information:

* Team ID: UJDHBB2D6Q
* Kernel Extension Bundle ID: com.thycotic.ThycoticACS

### II. KEXT Privacy Preferences Policy Control (PPPC) Full Disk Access Payload

Inside your MDM create a PPPC profile based on below:

* Identifier: com.thycotic.ThycoticACS
* Identifier Type: Bundle ID
* Code Requirement:

```text
anchor apple generic and identifier "com.thycotic.ThycoticACS" and (certificate leaf[field.1.2.840.113635.100.6.1.9] /* exists */ or certificate 1[field.1.2.840.113635.100.6.2.6] /* exists */ and certificate leaf[field.1.2.840.113635.100.6.1.13] /* exists */ and certificate leaf[subject.OU] = UJDHBB2D6Q)
```
