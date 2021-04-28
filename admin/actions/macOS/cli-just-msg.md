[title]: # (CLI Justification)
[tags]: # (action,macOS)
[priority]: # (3)

# Command Line Justification Message Action

This message action prompts the user for a justification when using Terminal to execute commands and scripts under `sudo`. This action is specifically designed to work with the Thycotic macOS sudo plugin and is only intended for commands that run under `sudo` based on the following use case:

* the user runs `sudo <command>`
* the user is prompted to supply a justification, which happens directly in the same terminal
* the command is then run with elevation

To create the message action,

1. Navigate to __Admin | Actions__.
1. Click __Create Action__.
1. For __Platform__, select __macOS__.
1. For __Type__, select __Command Line Justification Message__.
1. Enter a name and description.
1. Click __Create__.

   ![alt](images/cli-just-msg-act.png "Command Line Justification Message action")
1. Under Settings, use the color tooling options and editor to add and customize your message prompt for the users.
1. Click __Save Changes__.

>**Note**: The Command Line Justification Message action is the preferred message action to elevate commands and scripts run under `sudo`.
