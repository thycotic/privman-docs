[title]: # (Specific Applications)
[tags]: # (deny,blacklist)
[priority]: # (4301)
# Specific Applications

To create a new policy that blocks specific applications, do the following steps:

1. Begin by selecting Deny (Blacklist) Applications from the Privilege Manager Dashboard.
2. Select Block Application by Name and click Next.
3. You will have to supply a application under File Name and/or File Path. Optionally you may choose a message to display to the user when they attempt to execute the target application. Once you feel satisfied to proceed, click Finish.
4. On the General tab, you can customize the name and description of your Policy and observe where it will be placed in Privilege Manager’s folder structure. You should enable the Policy by ticking the checkbox next to Enabled and you can decide on what priority the Policy should have in comparison to other Policies. The lower numbered Policies will apply before higher numbered Policies.
5. Click the Policy Enforcement tab. If you wish to ensure that this Policy will not affect system or service applications, select Applies to all processes. Otherwise, keeping the Applies to all processes setting disabled will force this policy to apply to only applications launched by the interactive user. Ensure all other boxes are unchecked here and click Save to finish creating your blacklist Policy.

Be sure to test the new policy on a few machines before you roll it out to the environment.
