[title]: # (Anti Virus Exclusions)
[tags]: # (recommendation)
[priority]: # (1502)
# Anti Virus Exclusions

For Privilege Manager users, we recommend several antivirus exclusions to maintain application performance and integrity. These guidelines apply to both real time and on-demand antivirus scanning.

## Directories

Exclude these directories from your antivirus filters to ensure Privilege Manager processes will not be blocked (or for a more granular approach to these exclusions, see the Client Item Database and Privilege Manager Application Control Agent Services sections at the end of this article):

```
%ProgramData%\Arellia\
%ProgramData%\Application Data\Arellia
%ProgramFiles%\Thycotic\
```

## Exclusions for Web Server

Exclude the following antivirus programs for Privilege Manager's web server, also sometimes called Thycotic Management Server (TMS):

### Temporary ASP.NET Files
Exclude the following directory to prevent degradation in performance and possible unexpected restarts of the Tms and TmsWorker IIS application pools:

`%SYSTEMROOT%\Microsoft.NET\Framework64\v4.0.30319\Temporary ASP.NET Files`

## Exclusions for Database Server

Exclude the following database files.

### SQL Server Data Files

These files contain data and typically have the following extensions:

* .mdf - primary data filegroups
* .ndf - secondary data filegroups
* .ldf - transaction log filegroups

### SQL Server Backup Files

These files contain the backup files and typically have the following extensions:

* .bak - database backup files
* .trn - transaction log backup files

By default, the directories that contain the Data and Backup files are located under `C:\Program Files\Microsoft SQL Server\MSSQL11.MSSQLSERVER\MSSQL`.

### SQL profiler trace files

These files contain SQL Profiler Trace log data and can be contained in any folder.

They usually have the file extension .trc.

## Exclusions for Managed Endpoints

Exclude the following for managed endpoints.

### Request Run As Administrator Registry Key

Privilege Manager Application Control installs a context menu item that allows executables to be "Request Run as Administrator."

This context menu is added under the following registry key which some antivirus programs incorrectly flag as malware:

`HKLM\SOFTWARE\Classes\exefile\Shell`

### Client Item Database

These directories contain the Thycotic Agent client item database and should be excluded from antivirus to prevent corruption:

* `%ProgramData%\Arellia\ClientItems`
* `%ProgramData%\Application Data\Arellia`

If required, you can further limit this exclusion to all files with the .db and .db-* extensions under this location.

### Privilege Manager Application Control Agent Service

Some antivirus products require that the Privilege Manager Application Control service be excluded from tamper protection rules because Application Control manipulates other applications which antivirus products may mistake as malicious.

`C:\Program Files\Thycotic\Agents\ApplicationControl\ArelliaACSvc.exe`
