[title]: # (Local Groups)
[tags]: # (Local Security,Groups)
[priority]: # (302)
# Local Groups

Every Computer Group is divided into Groups and Users. Both “Groups” and “Users” in this context refer to local accounts on the machines that are included in the Computer Group.

To see more details about the Windows Computers Group, either click on Windows Computers in the Local Security Home screen or in the left-hand navigation pane:

<User-added image>

This Computer Group’s page will give you pointers on what can be done with the users and local groups within this set of computers, and provide a high-level overview of the selected computer group based on Local Users, Local Groups, and the number of computers in the group.

>**Note**:
>When an agent registers, Local Security will automatically discover the local groups that exist on each machine.

## Create New Local Group

To create a new Group, select the Groups line item listed under the name of the intended Computer Group. 

1. At the right side of the page, click the Create Group button.

   <User-added image>

1. Enter a Group Name and click Add Group.

   <User-added image>

1. On your new group page, add a Description and select Save Changes. Privilege Manager will prompt you with a Confirm Navigation box. Click Yes.

## Details Tab

### Add Members to Local Group

The Local Group Details’ tab shows you the Group Name, Description, and Members that are part of this group. To edit your group details click Edit in the right-hand corner.

<User-added image>

When editing, you can add members to the group by clicking the Add Member button. Select the type to add (Domain User, Domain Group, Local User) and then toggle the available options from the user list. To finish click Add Member, then Save Changes.

### Manage Local Groups

Managing a local group means that you determine which accounts are in that group from the Local Security dashboard. In other words, if a group is being “managed,” the group membership will remain static and will no longer be able to be updated directly on the endpoint.

If a local group is unmanaged you will see a toggle box next to Manage Group that is unchecked. To Manage the group, click Edit from the Details tab and then check the Manage Group box. Click Save Changes, and Yes to Confirm Navigation. Changes to these settings may take up to 15 minutes to update on your endpoints.

<User-added image>

When managing a group, existing members and any that have been added to the policy will appear in the Members table. From the dropdown choose the operation to perform upon the user if found on the endpoint. Options to Ignore if found, Add if missing, or Remove if found can be selected. The last row defines what action to take on all other users and groups. This ensures exact membership can be defined and any other users or groups can be automatically removed. By default, all other users and groups will be ignored, keeping their membership intact so that this key operation does not occur automatically. Once saved, group membership is permanently defined. Updates made directly on the endpoint that break this policy will be immediately reverted.

## Statistics Tab
The Statistics’ tab for a local group highlights some quick visual statistics and links you to relevant reports based on key factors like how many computers from your network are included in this group and whether there have been changes made to the Group’s Membership within the specified period. Click on these graphs to drill down into more details.

>**Note**:
>The reports in the “Related Reports” sections are scoped to only include endpoints in the current computer group. To view reports across all computers, go to the Reports section of the product.

<User-added image>

## Audit Tab
The Audit tab is where you will find an audit record of all membership additions and deletions that have been made to your local groups.

<User-added image>
