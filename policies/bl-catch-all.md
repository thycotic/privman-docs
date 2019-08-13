[title]: # (- Catch-all Blacklist)
[tags]: # (deny)
[priority]: # (4604)
# Catch-all Blacklist

A catch-all blacklist is the last policy executed following the execution of a group of whitelist policies. This enables you to configure your whitelist to allow approved applications, like the Windows directory or other installed applications, and then to deny everything else, like applications downloaded from the internet or a thumb drive.

To create a catch-all blacklist policy, do the following steps:

1. Begin by selecting Policies from the Privilege Manager Dashboard.
2. Next, click Add New Policy.
3. Select Other Policies and click the Next button.
4. Select Empty Application Control Policy and click the Next button.
5. Provide a name and description for your Policy and click Create.
6. Set the Policy Priority to 99 so it applies after all other Policies.
7. Click the Condition tab and click the plus button under Exclusion Filters. Search for "LocalSystem and Service applications" and click Add at the bottom.
8. Click the Actions tab, click Add Action, search for "Deny Execute", select Deny Execute, and click Add.
9. Click the Policy Enforcement tab, ensure only Stage 2 processing is checked, and click Save.

If you are creating a new catch-all policy to be used in conjunction with whitelist policies, please verify that the whitelist is catching all system applications and that the new blacklist is the last policy executed. For additional safety you can define the exclude any parameter to exclude system and service applications.
