[title]: # (Client Item List Downloads)
[tags]: # (agents, keyset)
[priority]: # (2)
# Client Item List Downloads
When you run the UpdateClientItems.ps1 PowerShell script to update policies on a
machine you see errors below:

*Error: [FAILED] Downloading Windows Group Policies client item list - Keyset does not exist*
![Windows Group Policies](images\downloading-windows-group-policies/27d5e11b2d784cc002a3d98a1bf9be2a.png)

>**Note:** This will only affect systems prior to Privilege Manager 10.7.

## Resolve

1.  Navigate to the Machine(s) where you want to update the policy.

1.  Open the Agent Utility by going to `C:\Program
    Files\Thycotic\Agents\Agent`

    ![Windows Group Policies](images/downloading-windows-group-policies/5b622bbadb56ede54a985a0d32e2adfe.png)

    ![Windows Group Policies](images/downloading-windows-group-policies/9a45991972016fd0709841929464ba1a.png)

1.  Click **Update**.

    ![Windows Group Policies](images/downloading-windows-group-policies/b5475c3d041954ed3de15f80a3c6d5ac.png)
