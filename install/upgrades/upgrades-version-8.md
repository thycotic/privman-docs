[title]: # (8.2 to 10.4+ Upgrades)
[tags]: # (new version)
[priority]: # (1705)
# Upgrading from Arellia Management Server 8.2 to Privilege Manager 10.4 and up

Upgrading from our 8.2 version to Privilege Manager 10.4 and up can’t be done from `https://servername/Ams/Setup/`. To upgrade, we recommend using the same database and removing the old application before installing the new version. This can be done automatically or manually.

## Automatic Steps

1. Download http://tmsnuget.thycotic.com/Software/ThycoticTmsInstaller_10_0_1570.exe and run it on the web server where your existing Arellia Management Server 8.x version is installed.
1. Follow the prompts.
1. Once it completes, you’ll access the server at `https://servername/Tms/` instead of `https://servername/Ams/`.
1. Go to `https://servername/Tms/Setup` to install the latest 10.x version.
1. Open __IIS Manager__ and go to __Sites__  | __Ams__ | __Agent__ | __Uploads__.
1. Click on the __BITS Uploads__ and change the notification URL from `http://localhost/Ams/Services/BitsUpload.ashx` to `http://localhost/Tms/Services/BitsUpload.ashx`.
1. Download and install and the latest agents. Please refer to the agent installation section [the lastest agent installation](../agents/index.md).
   >**Note**: Old agents will continue to work because of the redirect created during the install that sends traffic from `https://servername/Ams/Agent` to `https://servername/Tms/Agent`.
When upgrading the agents, we recommend that you set the __AMSURL__ to the new `https://servername/Tms/` address.

## Manual Steps

1. Remove the AMS website from the web server.
1. Download the latest bundled installer http://thycotic.com/products/secret-server/resources/download-secret-server/.
1. Follow the prompts to install Privilege Manager, setting the database connection to the existing database.
1. Download and deploy the latest agents that are [available here](../agents/index.md).
   >**Note**: Set the AMSURL to the new server address, https://servername/Tms/
