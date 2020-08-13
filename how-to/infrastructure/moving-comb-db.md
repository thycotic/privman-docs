[title]: # (Moving SQL DB)
[tags]: # (combined installation)
[priority]: # (2)
# Moving SQL DB

If you have a combined installation of Privilege Manager and Secret Server and wish to move/migrate the MS SQL Server databases, follow the steps below for the case that applies to you:

* __Case I__: Keeping all data in the current database:
  Backup the existing databases and restore them to the new SQL Server using the instructions below:
  * For Privilege Manager: see Moving the Privilege Manager DB topic below.
  * For Secret Server: https://thycotic.force.com/support/s/article/Moving-Microsoft-SQL-Server-Database-to-another-machine 

  If you have successfully performed the backup and restore (per the applicable instructions above), your site will be connected to the new database.

* __Case II__: Abandoning all data and starting fresh:

  1. In Privilege Manager, go to `https:// <SERVERNAME>/Tms/Setup/Database/ConnectDatabase`
  1. Provide the new database connection and click __OK__
  1. Install desired Thycotic products like Privilege Manager and/or Secret Server.

## Moving the Privilege Manager DB

### Step 1: Backup and Restore the Database

1. Stop the TMS site (Ams site for Arellia) in Internet Information Server (IIS) to prevent any changes to the database
1. Stop the TMS, TMSAgent, and TMSWorker application pools (Ams and AmsWorker application pools for Arellia).
1. Back up the database by accessing SQL Management Studio and right-clicking on the database to select Tasks > Back Up.
1. Select a file location for the .bak file. Transfer this file to the new server.
1. On the new database server, through SQL Management Studio, restore the database backup (the .bak file).
1. Create and/or grant access to the account that will be accessing the database (see TMS Installation Guide for account creation instructions)

We recommend taking the old database offline.

### Step 2: Connect to the new database (configure the database connection details)

1. Restart TMS website.
1. Check that the TMS, TMSAgent, and TMSWorker application pools are running.
1. Browse to your TMS URL database connection page e.g. `https:// <YOUR_URL_INSTANCE>/TMS/setup/database/connectdatabase` (for Arellia this URL would be slightly different e.g. `https:// <YOUR_URL_INSTANCE>/ams/setup/database/connectdatabase`) and you will see a page to enter your new database connection details.
1. Enter your new SQL Server and the account information.
1. Click Next and the site will connect to the new database.

Your site is now pointing to the new database.

If also migrating to new web servers or doing a reinstallation, copy the tmsEncryption.config file(s) to the new web servers(s). The file is located on the web server at the root of the TMS web site and should be copied to the same place on the destination server(s): `\inetpub\wwwroot\TMS` 
This file is only applicable if current servers are on version 10.5 or higher. (refer to [Item Encryption](../../install/installation/item-encryption.md))

To roll back changes and restore the original database, simply start back at Step 1 and move the database back to the original database server.
