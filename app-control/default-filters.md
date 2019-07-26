[title]: # (List of Filters)
[tags]: # (overview,out-of-box)
[priority]: # (5801)
# List of Filters

This topic provides a catalog of the out-of-the-box filters that are baked into Privilege Manager and can be used to make your policy configuration process easy.

## Filter Types and Descriptions

There are different types of filters. When creating a new filter for Windows, the "Filter Type" dropdown gives you a list of options that include the
categories:

* Application Filters
* File Filters
* Inventory Filters.

These are loose groupings that signify a few different approaches to the filtering method or targets. 

### Application Filters

These generally target specific executables or things about the environment. These types of filters can be used to limit policies to a certain time of day, the parent process of an application, the security rating of an application, or the user or group running the process.

* __Blank Win32 Executable Filter__ - Identifies specific application files by file name, file path, or common .exe file attributes.

* __Commandline Filter__ - These filters will perform an exact, partial or regex match on the commandline of the process.

* __Download Source Filter__ - Where is a file being downloaded from? This filter allows you to identify specific download sources, and allows the ability to whitelist sources you trust or block sources you don’t. *No out-of-box filters exist in Privilege Manager for this type*.

* __Environment Variable Filter__ - This type of filter can target environment variables of the process.

* __Network Location Filter__ - This type of filter identifies a computer's connection to specific networks like public, private, or unclassified networks.

* __Parent Process Filter__ - This type of filter can identify parent systems of certain executables.

* __Secondary File Filter__ - Secondary files are not an executable file itself, but another file that is being accessed or used as a command-line parameter for the process such as a script file or MSI installable package.

* __Security Rating Filter__ - If you have integrated Privilege Manager with a Reputation Checking tool like VirusTotal, these filters allow you to look up a rating for a file or application (is it good, bad, suspect/suspicious, or unknown)

* __Signed File Filter__ - This filter allows you to choose a Certificate or Multiple Certificates that are trusted and then verify that an applications is signed by one of those certificates. *No out-of-box filters exist in Privilege Manager for this type*.

* __Time of Day Filter__ - This type of filter exists to create policy parameters for specific timeframes like weekday or weekend hours.

* __User Context Filter__ - This type of filter is used to target users that belong to a specific user group.

### File Filters

These target specific file information. File Filters can be used to target the file owner of the application, the type of file, the application manifest of the file, or whether the application is present in the signed security catalog (Operating System Files).

* __Application Compatibility Filter__ - This type of filter identifies the rights or permissions that an application requires to run.

* __Application Manifest Filter (“Manifest Filter”)__ - Applications that declare specific rights required via a manifest, such as applications that need administrative privileges. 

* __File Collection Security Catalog Filter__ - This is a special collection of files to whitelist or blacklist. This filter type is similar to other Inventory Filters, particularly our Security Catalog Filter. *No out-of-box filters exist in Privilege Manager for this type*.

* __File Existence Filter__ - This type of filter identifies whether a file exists. *No out-of-box filters exist in Privilege Manager for this type*.

* __File Owner Filter__ - This filter identifies files based on ownership.

* __File Specification Filter__ - This filter identifies files based on their file path, or location on a computer.

* __File Type Filter__ - This filter identifies files based on what type of file it is. *No out-of-box filters exist in Privilege Manager for this type*.

* __Internet Zone Filter__ - This filter identifies what internet zone a computer is connected to on your network, such as Trusted Sites and Local Intranet. *No out-of-box filters exist in Privilege Manager for this type*.

* __Security Catalog Filter__ - This is a special collection of files to whitelist or blacklist. For example, the Microsoft Security Catalog is often whitelisted as a trusted catalog.

### Inventory Filters

These depend on file inventory data, meaning they generally apply to already discovered applications or files pulled in by Privilege Manager tasks. For example, after running an inventory task on a specific computer or group of computers, Privilege Manager can glean through the list of file inventory that is reported and target those files. *No out-of-box filters exist in Privilege Manager for this type of filter category*.

* __File Collection from List of Sha1 Hashes Filter__ - This type of filter identifies file inventory based on Secure Hash Algorithms. *No out-of-box filters exist in Privilege Manager for this type*.

* __File Scan Results Filter (Computer)__ - This type of filter identifies file inventory based on another computer's file scan results. This allows for one computer that has been setup properly to be used as a source for this filter. *No out-of-box filters exist in Privilege Manager for this type*.

* __File Scan Results Filter (Policy)__ - This type of filter identifies file inventory based on Privilege Manager Policies. *No out-of-box filters exist in Privilege Manager for this type*.

* __MSI File Contents Filter__ - This type of filter identifies file inventory based on .MSI file contents, i.e. specific Windows package installers. *No out-of-box filters exist in Privilege Manager for this type*..

* __Package Contents Filter__ - This type of filter identifies file inventory based on package contents. *No out-of-box filters exist in Privilege Manager for this type*.

* __Security Catalog Contents Filter__ - This is a special collection of files to whitelist or blacklist. This filter type is similar to other Inventory Filters, particularly our Security Catalog Filter. *No out-of-box filters exist in Privilege Manager for this type*.

* __Virtual Disk File Contents Filter__ -  *No out-of-box filters exist in Privilege Manager for this type*.

* __Virtual Disk Package Contents Filter__ -  *No out-of-box filters exist in Privilege Manager for this type*.

### macOS Specific Filters

* __App Bundle Filter__ - This type of filter identifies app bundles for MacOS machines.

* __Mach-O Header Filter__ - This type of filter identifies files based on their Mach-O file header details that declare it as a specific type of executable such as daemon, device driver, etc. 

## Filters Catalog

Here is a list of Privilege Manager out-of-the-box filters and descriptions, according to type.

### Win32 Executable Filters

| Filter | Description |
| ----- | ----- |
| __MS OIS__ | Filter used to identify the Office Picture Manager Image Viewer |
| __Add Hardware Utility (hdwwwiz.exe)__ | Filter used to identify the Device Pairing Wizard that appears when you click Add Device in Windows Vista and Windows 7 |
| __AppCmd for App Pool Recycling (appcmd.exe)__ | Filter used to identify the AppCmd executable|
| __Backup and Restore Utility (sdcit.exe)__  | Filter used to identify the Windows Backup and Restore utility |
| __Chrome__ | Filter used to detect Google Chrome web browsers |
| __COM Elevation Host Utility (COMElevateHost.exe)__ | Filter to detect the COMElevateHost. This is used to detect when COM components are being elevated, such as the Network Adapter Properties |
| __Command Processor (cmd.exe)__ | Filter used to identify the Windows command shell processor |
| __Control Panel Utility (control.exe)__| Filter used to identify the process used to launch Control Panel applets |
| __Defragment GUI Utility (dfrgui.exe)__| Filter used to identify the disk defragment utility within Windows|
| __Device Pairing Wizard__ | Filter used to identity the Device Pairing Wizard that appears when you click Add Device in Windows Vista and Windows 7 |
| __Eudora__ | Filter used to detect Eudora email client  |
| __Firefox__ | Filter used to detect Firefox web browsers |
| __Google Talk__ | Filter used to detect Google Talk |
| __IIS Manager Executable Filter (inetmgr.exe)__| Filter used to identify the IIS Manager executable|
| __IIS Reset Executable Filter (iisreset.exe)__ | Filter used to identify the IIS Reset executable |
| __Internet Explorer__| Filter used to detect Internet Explorer web browsers|
| __ISCSI Executable Filter (iscsicpl.exe)__  | Filter used to identify the ISCSI executable|
| __iTunes__ | Filter used to detect iTunes  |
| __Library Loader Utility (rundlll32.exe)__  | Filter used to identify the dynamic library loader utility used by Windows to launch various system configuration applets |
| __Microsoft Installer File Filter__ | Filter used to detect the Microsoft Installer. This filter can be used in policies with secondary file filters targeting specific MSI files |
| __Microsoft Management Console (mmc.exe)__  | Filter used to identify the Microsoft Management Console Utility |
| __Microsoft Windows Media Player__| Filter used to detect Windows Media Player |
| __MS Access__| Filter used to detect Microsoft Access |
| __MS Excel__ | Filter used to detect Microsoft Excel|
| __MS FrontPage__  | Filter used to detect Microsoft FrontPage  |
| __MS InfoPath__ | Filter used to detect Microsoft InfoPath |
| __MS Lync__ | Filter used to detect Microsoft Lync |
| __AOL Instant Messenger__ | Filter used to detect AOL Messenger |
| __MS Outlook__| Filter used to detect Microsoft Outlook|
| __MS Powerpoint__ | Filter used to detect Microsoft PowerPoint |
| __MS PPTVIEW__| Filter used to detect Microsoft PowerPoint Viewer |
| __MS Publisher__  | Filter used to detect Microsoft Publisher  |
| __MS Visio__ | Filter used to detect Microsoft Visio|
| __MS VPreview__ | Filter used to detect Microsoft VPreview |
| __MS Word__ | Filter used to detect Microsoft Word |
| __MSN Messenger__ | Filter used to detect MSN Messenger |
| __NLB executable Filter (nlbmgr.exe)__ | Filter used to identify the NLB Manager executable|
| __OODBC Executable Filter (odbcad32.exe)__  | Filter used to identify the OODBC executable|
| __Opera__ | Filter used to detect the Opera Browser|
| __Outlook Express__| Filter used to detect Microsoft Outlook Express  |
| __Performance Monitor Utility (perfmon.exe)__| Filter used to identify the Performance Monitor launcher stub utility within Windows |
| __Powershell (powershell.exe)__ | Filter used to identify the Windows Powershell command processor |
| __Printer Control Utility (printui.exe)__ | Filter used to identify the printer management applet launcher within Windows |
| __QuickTime__| Filter used to detect QuickTime|
| __RealPlayer__| Filter used to detect RealPlayer|
| __Resource Monitor (resmon.exe)__ | Filter used to identify the Windows Resource Monitor application |
| __Safari__ | Filter used to detect Apple Safari on Windows|
| __Scripting Host (cscript.exe)__| Filter used to identify the Windows Scripting Host command-line utility |
| __Scripting Host (wscript.exe)__| Filter used to identify the Windows Scripting Host commandline utility  |
| __Setup Display Languages Utility (lpksetup.exe)__ | Filter used to identify the Install/Uninstall of Display Languages setup utility for Windows|
| __ShareX__ | This filter targets the ShareX application |
| __Skype__ | Filter used to detect Skype |
| __Trillian__ | Filter used to detect the Trillian application |
| __User’s Temp Directory Win32 Executable Filter__  | Filter used to target any executable (exe) in a user’s temp directory |
| __Win32 Executables Discovered in the Last Week__  | This filter is limited to applications discovered on the endpoint within the last week|
| __Winamp__ | Filter used to detect Winamp application |
| __Windows Firewall (netsh.exe)__| Filter used to identify the Windows Firewall netsh.exe  |
| __Windows Messenger__| Filter used to detect Windows Messenger|
| __Yahoo! Messenger__ | Filter used to detect Yahoo Messenger|

### Commandline Filters

| Filter | Description |
| ----- | ----- |
| __Napclfcfg.msc Commandline Filter for MMC Snap-in__  | Filter used to detect NAP Client Configuration |
| __Add Printer Commandline Arguments__| Filter used to identify the Add Printer UI applet  |
| __Backup and Restore Commandline Arguments__| Filter used to identify the Backup and Restore component, used as a commandline argument to a process |
| __Certmgr.msc Commandline Filter for MMC Snap-in__| Filter used to detect Windows Certificate Manager  |
| __Ciadv.msc Commandline Filter for MMC Snap-in__ | Filter used to detect Indexing Service Management  |
| __Compmgmt.msc Commandline Filter for MMC Snap-in__ | Filter used to detect Windows Computer Management  |
| __Defragment Component (dfrg.msc)__ | Filter used to detect the MMC Snap-in used to defragment disks in Windows XP|
| __Devmgmt.msc Commandline Filter for MMC Snap-in__| Filter used to detect Device Manager  |
| __Dhcpmgmt.msc Commandline Filter for MMC Snap-in__ | Filter used to detect DHCP Management |
| __Diskmgmt.msc Commandline Filter for MMC Snap-in__ | Filter used to detect Disk Management |
| __Dnsmgmt.msc Commandline Filter for MMC Snap-in__| Filter used to detect DNS Management  |
| __Eventvwr.msc Commandline Filter for MMC Snap-in__ | Filter used to detect Event Viewer|
| __Fsmgmt.msc Commandline Filter for MMC Snap-in__| Filter used to detect Shared Folders Management|
| __Fsrm.msc Commandline Filter for MMC Snap-in__ | Filter used to detect File Resource Manager |
| __Gpedit.msc Commandline Filter for MMC Snap-in__| Filter used to detect Group Policy Editor |
| __Hardware Wizard Applet__  | Filter used to identify a commandline argument referring to the Control Panel applet used to add new hardware|
| __Lusrmgr.msc Commandline Filter for MMC Snap-in__| Filter used to detect Local User and Group Management |
| __Azman.msc Commandline Filter for MMC Snap-in__ | Filter used to detect Windows Authorization Manager |
| __Network Adapter Elevate Attempt__ | Filter used to detect when a user right-clicks on a network adapter and selects Properties |
| __Ntmsmgr.msc Commandline Filter for MMC Snap-in__| Filter used to detect Removable Storage Manager|
| __Performance Monitor Component (perfmon.msc)__ | Filter used to detect Performance Monitor |
| __Printmanagement.msc Commandline Filter for MMC Snap-in__ | Filter used to detect Print Management |
| __Recycle App Pool Commandline__ | Filter used to identify the recycle command for application pools  |
| __Rsop.msc Commandline Filter for MMC Snap-in__ | Filter used to detect Resultant Set of Policy|
| __Secpol.msc Commandline Filter for MMC Snap-in__| Filter used to detect Local Security Settings Manager |
| __Services.msc Commandline Filter for MMC Snap-in__ | Filter used to detect Services Manager |
| __Sqlservermanager12.msc Commandline Filter for MMC Snap-in__ | Filter used to detect SQL Server Manager|
| __System Control Panel Applet__| Filter used to identify a commandline argument referring to the Control Panel applet used to change the system time and date settings |
| __Tpm.msc Commandline Filter for MMC Snap-in__  | Filter used to detect Trusted Platform Module Management|
| __Wbadmin.msc Commandline Filter for MMC Snap-in__| Filter used to detect Windows Server Backup |
| __Wf.msc Commandline Filter for MMC Snap-in__ | Filter used to detect Windows Firewall Management  |
| __Wmimgmt.msc Commandline Filter for MMC Snap-in__| Filter used to detect WMI Management  |
  
### Environment Filters

| Filter | Description |
| ----- | ----- |
| __Manual Application Compatibility Setting__ | Detects whether an application is being run with manual override options |
| __User Access Control Consent Dialog Detected__ | This filter will match when an application that requires User Access Control consent is launched |
| __User Requested Run As Administrator__ | Detects whether a user has right-clicked on an application and used Thycotic’s custom ‘Request Run as Administrator’ option |

### Network Location Filters

| Filter | Description |
| ----- | ----- |
| __Disconnected from Network__| Filter used to detect when the computer is not attached to a network |
| __Domain Network Location Filter__ | Filter used to detect when the computer is attached to a network classified as domain |
| __Private Network Location Filter__ | Filter used to detect when the computer is attached to a network classified as private |
| __Public Network Location Filter__ | Filter used to detect when the computer is attached to a network classified as public |

### Parent Process Filters

| Filter | Description |
| ----- | ----- |
| __Thycotic Copy/Installer Helper Parent Process Filter__ | Filter used to detect when a user attempts to copy a file using the Privilege Manager copy helper |

### Secondary File Filters

| Filter | Description |
| ----- | ----- |
| __Application Signed By Certificates Secondary Filter for policy: New Whitelist Signed Applications Policy__  | Filter used to capture secondary files (such as MSI or scripts) for policy: ‘New Whitelist Signed Applications Policy’. This policy will add administrator rights to applications signed by the chosen certificates|
| __Application Signed By Certificates Secondary Filter for policy: Whitelist Microsoft Security Catalog Applications__ | Filter to capture secondary files (such as MSI or scripts) for policy: ‘Whitelist Microsoft Security Catalog Applications’. This policy will add administrator rights to applications signed by the chosen certificates |
| __Target MSI and Scripts executed from the User’s Temp Directory__ | Filter used to target MSI and Scripts executed from the User’s Temp Directory |

### Security Rating Filters

| Filter | Description |
| ----- | ----- |
| __VirusTotal__  | This filter will target VirusTotal for Reputation Checking |
| __VirusTotal-Bad Rating__| This filter will target VirusTotal for Reputation Checking |
| __VirusTotal-Clean Rating__  | This filter will target VirusTotal for Reputation Checking |
| __VirusTotal-Suspect Rating__ | This filter will target VirusTotal for Reputation Checking |

VirusTotal Filters based on configuring VirusTotal integration in Privilege Manager. For steps to do this, see our *VirusTotal Integration Guide here* 

### Time of Day Filters

| Filter | Description |
| ----- | ----- |
| __Business Hours (8:30AM to 5:30PM)__ | This filter is limited to 8AM to 6PM weekdays |
| __Business Hours (8AM to 6PM)__| This filter is limited to 8AM to 6PM weekdays |
| __Business Hours (9AM to 5PM)__| This filter is limited to 9AM to 5PM weekdays |
| __Weekends__| This filter is limited to weekends|

### User Context Filters

| Filter | Description |
| ----- | ----- |
| __Administrators__| Detects when an application is running with elevated (administrator) permissions |
| __Administrators (Include Disabled)__ | Detects when an application has an administrator user token |

## File Filters

### Application Compatibility File Filters

| Filter | Description |
| ----- | ----- |
| __Administrative Rights Required Application Compatibility Filter__ | This filter tests whether Windows has detected that this executable requires administrative rights |
| __Generic Installer Detection Filter__ | This filter indicates that Windows has detected that an executable is an Application Setup|
| __Highest Available Application Compatibility Filter__ | This filter tests whether Windows has detected that this executable required highest available rights |
| __Specific Installer Detection Filter__  | This filter indicates that Windows has detected that an executable is an Application Setup|
| __Specific Non Installer Detection Filter__| This filter indicates that an executable has been flagged as not being an Application Setup |

### Manifest Filters

| Filter | Description |
| ----- | ----- |
| __Require Administrator Rights Manifest Filter__| This filter tests whether an executable is marked as requiring Administrative rights |
| __Require Highest Available Rights Manifest Filter__ | This filter tests whether an executable is marked as requiring highest available rights |
| __Manifest Present Filter__| This filter tests whether an executable has a security manifest|

### File Owner Filters

| Filter | Description |
| ----- | ----- |
| __System (Wheel) File Owner__ | Files that are owned by the Wheel Group (Unix) |
| __System File Owner Filter__| Filter used to detect files owned by the System account|
| __Trusted Installer File Owner Filter__ | Filter used to detect files owned by the Trusted File Owner account |

### File Specification Filters

| Filter | Description |
| ----- | ----- |
| __Removable Drive Filter__  | Filters files present on removable drives such as Floppy Drives and USB devices |
| __Any Package (MacOS)__| Target .pkg and .mpkg files |
| __Common Executable Folders__| Filter used to detect files in common executable directories, such as C:\Windows, C:\Program Files, and C:\Program Files(x86) |
| __Date and Time Preference Pane (MacOS)__ | Date and Time Preference Pane (MacOS) |
| __Default App Bundles File Specification Filter__| The default filter for discovering app bundles on MacOS|
| __Default File Specification (All executable types)__ | Specifies all executable file types in Windows and Program files |
| __Default File Specification (MacOS)__ | The default filter for discovering executable files on MacOS |
| __Default File Specification (Windows)__ | This specifies executables in Windows and Program files|
| __Documents and Settings__  | Filter used to detect files in the Downloaded Program Files directory |
| __Drivers__  | Filter used to detect files in the C:\Windows\System32\drivers directory|
| __Energy Saver Preference Pane (MacOS)__ | Filter used to detect the Energy Saver Preference Pane in Mac |
| __Executables in Windows Directories__ | This specifies executables in Windows directories|
| __Executables in Windows Directories (All executable types)__ | Specifies all executable file types in Windows directories that are not present in a signed security catalog |
| __Mac OS/Users/File Specification__ | The default filter for files in the /Users/directory on MacOS |
| __Network Drive Filter__| Specifies files present on network file systems |
| __Optical Drive Filter (CD/DVD)__  | Specifies files present on optical drives (CD/DVD)|
| __Parental Controls Preference Pane (MacOS)__ | Filter used to detect the Parental Controls Preference Pane in Mac |
| __Printers and Scanners Preference Pane (MacOS)__| Filter used to detect the Printers and Scanners Preference Pane in Mac|
| __Program Data__| Filter used to detect files in the C:\ProgramData\ directory|
| __Program Files__ | Filter used to detect files in the C:\Program Files\ directory |
| __Program Files (x64 on Win32)__ | Filter used to detect files in the C:\Program Files\ directory |
| __Program Files (x86)__| Filter used to detect files in the C:\Program Files(x86)\ directory |
| __App Store Preference Pane (MacOS)__| Filter used to detect App Store Preference Pane in Mac |
| __Security and Privacy Preference Pane (MacOS)__ | Filter used to detect Security and Privacy Preference Pane in Mac  |
| __Sharing Preference Pane (MacOS)__ | Filter used to detect the Sharing Preference Pane in Mac |
| __System Catalog Folder__ | Filter used to detect files in the CatRoot directory  |
| __System Preferences (MacOS)__ | Filter used to detect the System Preferences Preference Pane in Mac |
| __Temporary __[ASP.NET](http://asp.net/)__ 1.0 Files__ | Filter used to detect files in the .NET 1 Temp directory |
| __Temporary __[ASP.NET](http://asp.net/)__ 1.1 Files__ | Filter used to detect files in the .NET 1.1 Temp directory |
| __Temporary __[ASP.NET](http://asp.net/)__ 2.0 Files__ | Filter used to detect files in the .NET 2 Temp directory |
| __Temporary Files__ | Filter used to detect files in the C:\Windows\Temp directory|
| __Thycotic Copy/Installer Helper Application__  | Filter used to detect usage of the Privilege Manager copy helper |
| __Time Machine Preference Pane (MacOS)__ | Filter used to detect the Time Machine Preference Pane in Mac |
| __Uncommon Executables Folders__ | Filter used to detect files in the Uncommon directories|
| __Users and Groups Preference Pane (MacOS)__| Filter used to detect the Users and Groups Preference Pane in Mac  |
| __User’s Directory Collection File Specification Filter__| Used to target any file in the user’s temp directory  |
| __User’s Downloads Directory File Specification Filter__ | Used to target any file in the user’s temp directory  |
| __User’s Temp Directory File Specification Filter__ | Used to target any file in the user’s temp directory  |
| __Windows Directory__ | Filter used to detect files in the C:\Windows directory |
| __Windows Directory (Include Subdirectories)__  | Filter used to detect files in the C:\Windows\ directory |
| __Windows Dll Cache__ | Filter used to detect files in the C:\Windows\System32\dllcache directory|
| __Windows Side By Side__| Filter used to detect files in the C:\Windows\WinSxS\ directory |
| __Windows Software Distribution__  | Filter used to detect files in the Windows Software Distribution directory |
| __Windows\System32__ | Filter used to detect files in the C:\Windows\System32 directory |
| __Windows\System32 (Include Subdirectories)__  | Filter used to detect files in the C:\Windows\System32\ directory  |
| __Windows\SysWOW64__ | Filter used to detect files in the SysWOW64 directory |
| __Windows\SysWOW64 (Include Subdirectories)__  | Filter used to detect files in the SysWOW64\ directory|

### Security Catalog Filters

| Filter | Description |
| ----- | ----- |
| __Present in Signed Security Catalog__ | Filter used to detect Operating System Files and other trusted files dynamically on each system by using that machine’s Signed Security Catalog. This filter does not need to be modified on the server |

## Miscellaneous Filters

### App Bundle Filters

| Filter | Description |
| ----- | ----- |
| __All Application Bundles Filter (MacOS)__ | Filter used to detect All Applications Bundles |

### Coff Header Filters

| Filter | Description |
| ----- | ----- |
| __Native Executables__| Filter used to detect files with the executable header set |
| __Windows CE Executables__  | Filter used to detect files with the Windows CE Subtype header set|
| __32-bit Executables__| Filter used to detect files with the 32-bit executable machine type header set |
| __All Executable Types__| This filter includes all executable types|
| __Program File Executables__ | Filter used to detect files with the executable or DLL header set |
| __GUI Executables__  | Filter used to detect files with the GUI header set |
| __X64 Executables__  | Filter used to detect files with x64 machine type header set |
| __Commandline Executables__ | Filter used to detect files with the Windows console subsystem header set |
| __Posix Executables__ | Filter used to detect files with the POSIX header set|

### File Parameter Collections

| Filter | Description |
| ----- | ----- |
| __All Executables Discovered in Last Day__| Filter used to detect files that have been discovered by the server in the past day  |
| __All Executables Discovered in Last Week__ | Filter used to detect files that have been discovered by the server in the past week |
| __All Executables Discovered in Last Month__  | Filter used to detect files that have been discovered by the server in the past month |
| __All Greylist Security Rated Applications__  | This collection contains all applications that have been greylisted |
| __All Executables Discovered in Last 2 Weeks__ | Filter used to detect files that have been discovered by the server in the past 2 weeks|
| __All Blacklist Security Rated Applications__ | This collection contains all applications that have been blacklisted by applying a security rating |
| __All Whitelist Security Rated Applications__ | This collection contains all applications that have been whitelisted by applying a security rating |
| __All Unclassified Applications__ | This collection contains all applications that have not been classified by a security rating|

### Mach-O Header Filters

| Filter | Description |
| ----- | ----- |
| __macOS DyLib__| Identifies dynamic library (dylip) files according to their embedded Mach-O header (not specifically according to file name) |
| __macOS Executables__ | Identifies files marked as executables according to their Mach-O header (not file mode changes via chmod)|
