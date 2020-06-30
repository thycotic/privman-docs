[title]: # (Agent Trust Revocation)
[tags]: # (operations)
[priority]: # (4)
# Agent Trust Revocation

With Privilege Manager 10.5 and up, you can revoke an agent trust relationship.

## Revoking the Trust from the Server

1. Navigate to the Agent Install Code's page and click __Remove Agent Trust__.

   ![revoke server](images/ag-1.png "Revoke Agent Trust button")
1. Click __OK__ to confirm.

   ![confirm](images/ag-2.png "Confirm the revocation")

## Revoking the Trust for the Computer Resource

1. Navigate to __Admin | Agents__ to open the Agents Summary page.
1. Select an Operating System group from list.
1. On the Managed Computers by Operating System page, select one of the computer resources.

   ![revoke resource](../images/resource-explorer.png "Resource Explorer Revoke Agent Trust")
1. Click __Revoke Agent Trust__.

   ![confirm](images/resource-revoke.png "Confirm agent trust revocation")
1. Confirm by clicking __Revoke Agent Trust__. 

Message on the Revoke Agent Trust dialog:

"Revoking this agent's trust will disallow this computer from registering and receiving policies. This process cannot be undone. To later re-establish trust between this computer, you will need to re-install the agent with the proper install code.

This does not uninstall the agent from the computer, it simply denies it from contacting this server. This process also does not delete this agent nor its data from this server. Use the 'Delete' button from the Resource Explorer view to remove the computer and it's data from this server."
