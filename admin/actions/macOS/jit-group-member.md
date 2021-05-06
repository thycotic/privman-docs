[title]: # (JIT Group Membership)
[tags]: # (action,macOS)
[priority]: # (3)
# Just-in-Time Group Membership Action

This action will add a user to the specified group for a specified time. This action can then be added to a controlling policy to give Just-in-Time elevation to a user. The action is a read-only action by default. To customize this macOS action for your endpoints, use the __Duplicate__ option.

1. Navigate to __Admin | Actions__.
1. Search for and select __Just-in-Time Group Membership__ from the list of available macOS actions.
1. Click __Duplicate__.
1. Enter a name for your newly created action and click __Create__.

   ![jit](images/jit-gm.png "Just-in-Time Group Membership action")
1. Under __Settings__ specify
   1. the __Group Name__ as created on the endpoint.
   1. the __Duration__ either
      * set a specific length of time, here you need to consider that authorization is started when the application starts, or
      * use the default _as long as application is active_.
   1. enable the __Suppress password prompts from sudo while a member of the group__ if the user should __not__ be prompted for the standard user password while in the group.
1. Click __Save Changes__.

>**Note**: The _Suppress password prompts from sudo while a member of the group_ checkmark is intended for use with scripts that may execute multiple sudo commands, such as the Homebrew installer.

Refer to the topic [macOS Homebrew Installer Support](../../../computer-groups/macOS/examples/homebrew.md) for details on the policy setup.
