[title]: # (Hardening Rollback)
[tags]: # (endpoint,hardening)
[priority]: # (1621)
# Restore Default Agent Permissions

If you need to rollback agent hardening on your endpoints, follow these steps to restore the default agent permissions:

1. Navigate to __ADMIN | More...__ and select __Config Feeds__.
1. Next to __Privilege Manager Product Configuration Feeds__ click __Select Items__.
1. Next to __Thycotic Management Server Core__ click __Select Items__.
1. Download the __Reset Agent Service Permissions__ config feed.

   ![Config Feed](images/agent-har/cfg-feed.png "Download the Reset Agent Service Permissions config feed")
1. Once the config feed is installed, navigate to __ADMIN | Policies__ and select the General tab.
1. Search for the agent service policies and select to edit.

   ![Agent Service](images/agent-har/agent-service.png "Agent Service policies")
1. Disable the __Agent Service Start / Stop Control (Windows)__ policy.
   1. Click __Edit__.
   1. Deselect __Enabled__.

   ![Disable](images/agent-har/disable.png "Disable the Agent Service Start / Stop Control policy")
   1. Click __Save__.
1. Enable the __Agent Service Clear Restrictions (Windows)__ policy.
   1. Click __Edit__.
   1. Select __Enabled__.

   ![Clear Restrictions](images/agent-har/clear-restrict.png "Agent Service Clear Restrictions policy")
   1. On the Targets tab specify the computers that need to be targeted by this policy.
   1. On the Triggers tab specify when to run and/or what events will trigger the policy to run.
1. Click __Save__.

<!-- no go
1. Navigate to __ADMIN | More...__ and select __Folders__.
1. In the Policies folder tree open __General | Windows__.

   ![Rollback 1](images/agent-har/h-rollback-1.png "Policies Folders showing General | Windows node")
1. Click __Add New__.
1. From the __Template__ drop-down select __Local Security Scheduled Client Task__.
1. Name your policy _Restore Agent Security Permissions_.
1. As a command enter __Local Security Set Service Security Script__.
1. Click __Create__.

   ![Rollback 2](images/agent-har/h-rollback-2.png "Remote Schedule Client Command")
1. Click __Edit__.
1. Select the __Parameters__ tab.
1. For __Service__ add the __ArelliaAgent__ service.
1. For __Security Descriptor__ add the __Standard Service Security Descriptor__.
1. Click __Save__.

   ![Rollback 3](images/agent-har/h-rollback-3.png "ArelliaAgent Service and Security Descriptor")
1. Click __Create a Copy__.
1. Name the copy _Restore ACSAgent Security Permissions_.
1. Click __Create__.
1. Click __Edit__.
1. Select the __Parameters__ tab.
1. For __Service__ add the __ArelliaACScv__ service.

   ![Rollback 4](images/agent-har/h-rollback-3.png "ArelliaACSvc Service")
1. Click __Save__.

Add the Remote Scheduled Client Commands to a policy to have the agents pick up the rollback.
-->