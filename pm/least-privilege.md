[title]: # (Least Privilege Overview)
[tags]: # (Least Privilege, Overview)
[priority]: # (12) 
# What is Least Privilege?

Least Privilege is a security-driven management philosophy that models a system where all employees are given the minimum level of access rights necessary to carry out their job functions on endpoint machines. This is to protect each machine from malicious applications, rogue employees, or attackers. Privileged local admin or root accounts on endpoints give unfettered access to the entire endpoint and can potentially be used to access other computers, domain resources, and critical servers unless a least privilege security model is implemented.  But implementing Least Privilege can be difficult for IT teams to enforce because there are plenty of daily, trusted activities that employees must perform that require access to privileged credentials.

Privilege Manager’s toolset is two-fold. First, Local Security discovers all accounts that exist on endpoints and allows Privilege Manager Administrators to control the exact membership of every local group. This will ensure the correct admin and root accounts are permanently set. Additionally, credentials will be controlled by enforcing password rotation on those accounts.

Second, Application Control allows Privilege Manager administrators to manage application activity on endpoint machines. Applications that require admin rights or root access can be automatically elevated, allowed applications are whitelisted, and malicious applications are blocked.

In other words, tailoring a robust, role-based Application Control system is key to keeping your organization’s employees working both securely and effectively, without notable disruptions. But managing local administrator and root accounts through Local Security is arguably the fastest way to lock down your network from malicious endpoint attacks that exploit administrator access.

## Rollout Recommendation

That’s why Thycotic recommends a phased roll-out between the two sides of this equation. As example:

1. Application Control: Set up learning mode policies on a group of test endpoints to learn about applications running on your endpoint machines (Event Discovery | Learning Mode Policies – Send Policy Feedback)
1. Local Security: Begin managing your local user accounts (only) and defining local group membership (Local Security | Manage Local Users) 
1. Application Control: Tailor your policies so that they won’t disrupt employee work (Creating Policies | Elevation Policies) but will block known malicious applications (Creating Policies | Example: Quarantine Specified Malware). Implement these basic policies across agents in production 
1. Application Control: Continue to tailor policies according to employee roles. Create a “Request Access” system for any unknown applications. (Creating Policies | Example: Application Execution Requires Approval (Workflow))
1. Local Security: Once a workflow has been established between employees and the Privilege Manager Helpdesk, begin managing all local privileged accounts (ex: local admins) on endpoints. (Local Security | Details Tab) 

>[!Note]
>Every implementation looks different when configuring Privilege Manager to work best for your organization. The key is to know your goal and be smart about getting there. The User Guide will walk you through beginning configurations for both Local Security and Application Control. Use it as a tutorial, reference, and guide for setting up a new environment until you get the hang of things, and always feel free to flip around.