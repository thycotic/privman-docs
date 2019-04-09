[title]: # (Computer Groups)
[tags]: # (Local Security,Computer Groups)
[priority]: # (301)
# Computer Groups

If you have agents already installed and registered, you will see numbers automatically listed in Local Security Home, divided by Privilege Manager’s two out-of-the-box computer groups that are listed as 

1) Windows Computers and
2) MacOS Computers.

For example, in the screenshot above only one agent is registered with Privilege Manager. Local Security tells us that the agent is installed on a Windows computer (thus categorized in the Windows Computers group), that there are 18 local User Groups, and 5 local Users on the machine. Local Security automatically discovers this information upon every agent’s registration with Privilege Manager.

If you have “Computer Groups” (also called Resource Targets) already configured for Application Control in Privilege Manager, keep in mind that those groups can also appear as Computer Groups in your Local Security navigation pane after selecting the “Show All Computer Groups” check box. Select the first column of any row to use the target endpoints as a Computer Group and display it in the left navigation panel.

## Create New Computer Group
To add new computer groups tailored to your organization’s environment, click the Create Computer Group button from the Local Security Home screen. Enter a Name for your new group, a Description, and select the Operating System (Windows vs Mac) used by these computers from the dropdown.

![Add New Computer Group](images/add-new-computer-group-20190408.png)

To select the machines you want to include within this group, you must create a Filter that will target the appropriate machines on your organization’s network.

![Filter Setup](images/add-new-computer-group-filter-20190408.png)

The default filter will begin with a rule that targets computers within the main OS Computer Group that was selected when you created the group, meaning it will target either all Windows or all Mac computers with registered agents.

To narrow your group, click Add Rule then in the “List Type” column select Computer List. Click any specific computers from the provided list of registered machines, then click Save. You may collapse the computer list view by clicking the button that says Select Computers under the Selected Items column.