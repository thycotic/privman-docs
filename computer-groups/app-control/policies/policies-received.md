[title]: # (Agent Policy State)
[tags]: # (agent)
[priority]: # (7)
# Agent Policy State

These are the steps for verifying which policies were received by an agent:

1. Navigate to __ADMIN | Agents__ and click on __Agent Policy State__.

   ![Agents overview](images/policy-state/agent-policy-state-1.png)
1. On the __Agent Policy State - Drilldown__ page select the computer, whose policy state you wish to examine.
1. This opens the Resource Explorer for the selected endpoint.

   ![Resource Explorer for selected computer](images/policy-state/agent-policy-state-2.png)

   On the __Policies on Endpoint__ tab you can view the polices that the agent on the endpoint has received. The Filter on the __Policy Name__ column allows you to search for specific policies.

   The columns __Has a Version of the Policy__ and __Has Current Version of the Policy__ provide information about the version of the policy.

   The column __Policy Last Modified__ informs when a policy was last changed.

   The column __Policy Applied to Agent__ specifies when the policy was first received by the agent.

   The column __Agent Last Received Policies__ informs when the agent last contacted the server to request updates.
