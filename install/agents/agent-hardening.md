[title]: # (Agent Hardening)
[tags]: # (endpoint,installation,registration)
[priority]: # (620)
# Agent Hardening

Agent installations on endpoints can be secured, only allowing a specified user access to start or stop an agent service and denying any agent control access to a local Administrator or basic user account.

To make sure that local Administrators do not tamper with Thycotic agents running on their system, Privilege Manager Administrators can define users that can start and stop the Privilege Manager services running on endpoints, such as the Thycotic Agent or Thycotic Application Control.

A user or group needs to be available in Privilege Manager to be selected while setting up the task. This user or group will have rights to start and stop agent services running on endpoints.

Refer to the topic on [Setting up the SDDL for Services by Account IDs Client Task](../../tasks/sddl-client.md).
