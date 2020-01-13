[title]: # (Installation)
[tags]: # (installation,basic)
[priority]: # (1503)
# Product Installation - Basic

## Prerequisites

### ASP.NET Website

Privilege Manager is installed as an ASP.NET website. The setup.exe file will set up the website with the correct permissions and create the settings in IIS.

### SQL Server Database

Thycotic products require an instance of SQL Server for the database backend and an instance of SQL Express will be installed by the setup.exe file if missing. The SQL Server database will require a SQL account with db_owner permission to complete the installation. SQL Express edition is intended for Sandbox and trial environments, Thycotic recommends purchasing SQL licensing for use in production environments.

### Administrative Access

Throughout the installation process, you will be required to be an administrator to perform most actions. Please ensure that you are logged onto your system with a Windows account that has administrative rights before beginning your install.

### Additional Recommendations

1. Use an SSL certificate for Privilege Manager.
1. Run Microsoft Update on your server to make sure all components are up to date.

## Download the Latest Version of PM Installer

The latest version of Privilege Manager is available for download under the [Software Downloads topic](../sw-downloads.md). It is recommended to run the downloaded setup.exe file as an administrator.

## Running the Installer

1. Double-click the downloaded setup.exe to run the installer. The installer opens on the __Welcome__ tab:

   ![Installation Welcome dialog](images/install/inst_welcome_20190327.png)

1. Verify that the Privilege Manager and Secret Server boxes are checked.

   >**Note**:
   >Although, installing Secret Server is optional, if you choose NOT to install Secret Server, you will not be able to create custom roles in Privilege Manager. Privilege Manager as a standalone product comes with three roles Administrator, Basic User, and Help Desk User roles.

1. Click Next to proceed to the License tab.
1. On the __License__ tab review the End User License Agreement (Eula) on the license page of the installation wizard.
1. Click Accept License to proceed to the Database tab.
1. On the __Database__ tab you can choose to either install SQL Express or connect to an existing SQL Server. SQL Express requires a internet access for the installer to download the installation package for SQL Express.

   >**Note**:
   >For production environments Thycotic recommends installing a licensed edition of SQL before installing Thycotic products. The Express edition is only recommended for trial and sandbox environments.

   * If Internet access is not available a link to download SQL Server Express will be presented to the user. At that point, they are expected to install SQL Server Express and then restart the installer.
   * If Internet Access is available SQL Server Express will be installed.
   * After SQL is installed select Connect to an existing SQL Server.

    ![SQL Server dialog](images/install/inst_sql_20190327.png)

1. The __Pre-Requisites__ tab makes sure everything that is required to install Privilege Manager is setup correctly. Everything on this page can be installed outside of the installer, but if not, the installer will install and configure them for the user. Think of this page as the non-Thycotic configuration. If there are issues with this page it is very likely that the Internet will be able to help as these are not installation features that are specific to Thycotic. Click Fix Issues to automatically install the necessary pre-requisites. When Successful, click Next.

   ![Prerequisites dialog](images/install/inst_prereq_20190327.png)

1. If you chose the “Connect to an existing SQL Server” option on the Database page, the __Database Connection__ tab will now prompt you for the connection information that Secret Server and/or Privilege Manager will use. The Test Connection button must be run successfully before installation can continue. Once connection is established, click Next.

   ![DB Connection dialog](images/install/inst_dbconnect_20190327.png)

   1. If you choose SQL Server Authentication, next the Account tab will prompt for the server location where your SQL database is currently installed. Provide the Server Name or IP address for your Database server and Authenticate with Administrator SQL credentials. If your Secret Server database does not yet exist when you click "Test Connection" the Installer will create it. When the connection has been tested successfully, click Next.

1. The __Email Server__ tab opens, here the connection information for the email server can be entered. This is also optional and can be skipped to be configured later in the application by clicking Skip Email. This page will configure email for both Secret Server and/or Privilege Manager.

   ![Email Server dialog](images/install/inst_email_20190327.png)

1. On the __Review__ tab, most settings are defaulted for a user and they can choose to modify settings at this step. Certain validations will occur on these settings before the install can begin. Click Install to proceed.

1. The Install page will show the status from log files as Secret Server and/or Privilege Manager are installed. Installs vary depending on your environment, most installs last between 20-60 minutes.

1. The __Log Files__ tab is available after the applications are installed. The installer provides the link to open a web browser to the product login page. At this point, everything is installed and ready for you to begin using your new Thycotic product. If the installation failed or you wish you view the logs from the installation you can click the View Log Files button.

1. On the __Finish__ tab, when the install has successfully completed, click the provided Privilege Manager URL to navigate directly to your setup landing page or open a browser and navigate to where your Privilege Manager is located, for example: http://localhost/TMS/PrivilegeManager.
