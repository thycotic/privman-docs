[title]: # (- Catch-All Policy)
[tags]: # (greylist)
[priority]: # (4501)
# Catch-All Policy

A useful Learning Mode Policy to set up in Production environments is called a Catch-All Policy. This type of policy will gather information on any executables in your environment that are not satisfied by other Privilege Manager policies.

1. Navigate to Home | New Policy, then select a platform.
1. From Policy Type select Show All Templates
1. For POC and testing environments, Select Other: Empty Policy Targeting Test Computers from Template Type option
1. Name the policy Catch-All Policy, and add a description
This policy will catch all processes not caught by any defined policy above it.  It should run at the highest policy priority (e.g. 100). 
1. Click Create
1. To Enable this policy, you’ll need to set up the Conditions, Actions, Policy Enforcement, and Deployment tabs. One version of a Catch-All Policy’s settings are demonstrated by the following screenshots
Conditions:
 
<TODO update screen captures>

Actions:
<TODO update screen captures>
Policy Enforcement:
<TODO update screen captures>
