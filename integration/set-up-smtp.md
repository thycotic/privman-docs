[title]: # (Set-up SMTP Connection)
[tags]: # (email server)
[priority]: # (9103)
# Set-up SMTP Connection

Simple Mail Transfer Protocol (SMTP) is the Internet standard for email transmission. Often organizations use an SMTP Server — or a server that is specifically dedicated to transmitting email messages via TCP Port 25 — and in order to send email alerts with Privilege Manager policies, you must ensure that your email server is connected to Privilege Manager.

## Configuring the SMTP Connection

To set up the connection, follow these steps:

1. Navigate to __Admin | Configuration | Foreign Systems__ (tab).
1. Click SMTP Server, then __Add New__.
1. Add the Name of your SMTP Server and the base Uri (ex: smtp://[hostname];[port]), then __Create__.

Next, in order to begin email alert notifications for a policy, you will need to assign a Task for the job. This example will set up Approval Requests with Email Alerts,

## Setting up Email Alerts

Email alerts can be created in __Admin | Tasks > Server Tasks > E-mail Tasks__, then __Add New__.

### Approval Requests

To set up email alerts for Approval Requests:

1. Navigate to __Admin | Tasks | Automation__ tab, then expand Approvals and select Approval Processes.
1. In the center section you will see options including Manual Approval Process with E-mail Alerts (If this option does not exist, click Add New to add it). Click this option and then __Edit__.
1. Enter the requested information. For the Start Activity, type Send E-mail for New Approval Task. For the SMTP Server, select the resource for the SMTP connection you created above, click __Save__.
