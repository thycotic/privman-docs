[title]: # (SMTP)
[tags]: # (email server)
[priority]: # (9103)
# Set-up SMTP Connection

Simple Mail Transfer Protocol (SMTP) is the Internet standard for email transmission. Often organizations use an SMTP Server — or a server that is specifically dedicated to transmitting email messages via TCP Port 25 — and in order to send email alerts with Privilege Manager policies, you must ensure that your email server is connected to Privilege Manager.

## SMTP in Cloud Environments

Starting with version 10.7.1 of Privilege Manager Cloud, the SMTP foreign system is automatically configured with the email server information as provided during the cloud instance set-up. The information can be added/changed following the initial set-up.

## Configuring the SMTP Connection

To set up the connection, follow these steps:

1. Navigate to __Admin | Configuration | Foreign Systems__ (tab).
1. Click SMTP Server, then __Add New__.
1. Add the Name of your SMTP Server and the base Uri (ex: smtp://[hostname];[port]), then __Create__.

Next, in order to begin email alert notifications for a policy, you will need to assign a Task for the job. The __Setting Up Email Alerts__ information below is just one example of tasks that can be configured for automated email notifications.

## Setting up Email Alerts

Email alerts can be created in __Admin | Tasks > Server Tasks > E-mail Tasks__, then __Add New__.

### Approval Requests

>**Note:**  For cloud environments the SMTP server settings are pulled from an existing configuration and can't be edited via the parameters tab.

1. Navigate to __Admin | Tasks | Automation__ tab, then expand Approvals and select Approval Processes.
1. In the center section you will see options including Manual Approval Process with E-mail Alerts (If this option does not exist, click Add New to add it). Click this option and then __Edit__.
1. Enter the requested information. For the Start Activity, type Send E-mail for New Approval Task. For the SMTP Server, select the resource for the SMTP connection you created above, click __Save__.
