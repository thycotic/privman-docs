[title]: # (Introduction to Privilege Manager)
[tags]: # (Privilege Manager,Introduction)
[priority]: # (1)
# Introduction to Privilege Manager

Privilege Manager is an endpoint least privilege and application control solution for Windows and Macs. The two major components are Local Security and Application Control.

Using Privilege Manager, administrators can automatically discover local administrator privileges and enforce the principle of least privilege through policy-driven actions. Those policy-driven actions include

* white-, black-, and gray-listing,
* application quarantine, sandbox, and isolation,
* application privilege elevation, and
* endpoint monitoring

All this is seamless for users, reduce IT/desktop support workload, and support compliance obligations.

Privilege Manager does not require Secret Server or any other Thycotic product to run. Secret Server's vaulting and workflow capabilities can be extended to privileged endpoint accounts when the two products are used together.

The typical Privilege Manager user is part of an IT team that is tasked with implementing and overseeing a company's security business requirements and framework. In the Privilege Manager product this role is known as the Privilege Manager Administrator. Although there are a few other kinds of Privilege Manager user roles (to be described further on) who may use Privilege Manager now and then for minor tasks, the Privilege Manager Administrator is the main user of Privilege Manager.

It is useful (although not necessary) for Privilege Manager Administrators to be familiar with the basics of IT administration, such as the Group Policy feature from Microsoft.

## Cloud 10.6 Specific

The following features and options are __not__ available in Privilege Manager Cloud 10.6:

* The Local Active Directory features exists, but requires a direct connection to the domain controller, which is often not permissible due to firewall configurations.
* Secret Server integration for authentication and vaulting of local account credentials is not presently available.
* All license key management is done via Thycotic and license keys are not visible on the licensing page. There are not presently options for customers to add additional licenses directly.
* Access to the Security Manager console (Silverlight version) is not available.
* Personas are not available.
* Server-side Powershell scripts not signed by Thycotic are not allowed. Custom server-side work can be done via Professional Services engagements.
* The setup is managed by Thycotic and installations, upgrades, and repairs are unavailable to the customer directly, this includes setup, add/remove feature options, and connection option to existing Secret Server. Upgrade notices and banners are removed with upgrades being handled by Thycotic during maintenance periods.

All other features and functionality of Privilege Manager On-premises and Cloud are the same unless otherwise specified.
