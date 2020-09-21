[title]: # (Best Practices)
[tags]: # (backups, troubleshooting)
[priority]: # (1654)
# Best Practices for Upgrades

## DB Backup

Thycotic recommends that Privilege Manager data bases are backed-up prior to an upgrade. For details SQL Database Back Up information refer to the vendor documentation of your SQL Database, such as [Back Up and Restore of SQL Server Databases](https://docs.microsoft.com/sql/relational-databases/backup-restore/back-up-and-restore-of-sql-server-databases?view=sql-server-ver15).

## TMS Folder Backup

Other measures to take before any upgrade are to make a backup copy of your Privilege Manager TMS folder and all it's contents.

1. On your Privilege Manager host system navigate to `C:\inetpub\wwwroot\TMS` (default installation location).
2. Create a backup copy of the TMS folder contents at another location on your system or network.

## Repair Solution

When running into an error condition during an upgrade, try the repair option for the specific solution that errored out.

Also refer to [Troubleshooting - Installation and Upgrade Issues](../../troubleshooting/install-upgrade/index.md).
