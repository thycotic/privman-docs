[title]: # (CLI Approval Message)
[tags]: # (actions,*nix)
[priority]: # (3)

# Command Line Approval Message Action

The Command Line Approval Message action allows administrators to prompt command line users on Unix/Linux endpoints for an approval request. The action displays text in the command line interface and prompts the user to enter text.

To create the message action,

1. Navigate to __Admin | Actions__.
1. Click __Create Action__.

   ![alt](images/cli-approval.png "Create Action modal")
1. For __Platform__, select __Unix/Linux__.
1. For __Type__, select __Command Line Approval Message__.
1. Enter a name and description.
1. Click __Create__.

   ![alt](images/cli-approval-msg.png "Approval message configuration page")
1. Under __Settings__ for:
   * __Message__, use the color tooling options and editor to add and customize your message prompt for the users.
   * __Approval Type__, from the drop-down select either
     * __Default Execute Application Request Type__ or
     * __Default Offline Execute Application Request Type__.
1. Click __Save Changes__.

Refer to [Using the Command Line Action Editor](../index.md#using_the_command_line_action_editor) for information on how to use the editor.
