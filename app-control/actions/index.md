[title]: # (Actions)
[tags]: # (overview)
[priority]: # (5500)
# Actions

In Privilege Manager, taking action is the name of the Application Control game.
Once you know how to accurately identify events via filters, the next crucial step in policy creation is to make stuff happen by applying specific actions to your filtered targets. This begs the question: what actions are possible to perform in Privilege Manager?

The most popular and well-known action categories in Application Control include:

* __Whitelisting Actions__ - This means allowing an executable to run on your network with normal user privileges.
* __Blacklisting Actions__ - A better word for this is “deny.” Blacklisting an application simply means: block it, or prevent it from running.
* __Greylisting Actions__ - This is a category of actions that can be applied to unknown applications that attempt to run. Sandboxing is another term often linked to Greylisting, because you can create policies that link to reputation checking tools (like VirusTotal) to perform smart actions once an unknown file’s reputation has been verified.
* __Elevation Actions__ - Allowing an application to run (Whitelisting) is good and well for trusted programs, but many trusted applications also require a higher credential set than your end users normally have access to. The elevation action category will allow an application to run with elevated permissions so any user can, for example, install that trusted HP printer on your network without taking time out of a HelpDesk employee’s day. Implementing elevation policies allow "Least Privilege" to be implemented by your organization, eliminating the need for local users to have full administrator access on their computer.
* __Workflow Actions__ - Some actions explicitly enforce an organization's workflow system. The big example here is the “Request Access” action that will prompt a user for the reason they are trying to access an application for verification purposes and auditing.
* __Display Message Actions__ - Display messages are paired with one of the action types listed above. Display Message Actions are customizable and serve to tell the end user what is happening and why.

For a more complete (and more specific) list of all out-of-the-box Privilege Manager actions and types of actions, see our Actions' Catalog here.

## Creating a New Action Manually

Navigate to Admin | Actions in Privilege Manager and click Add New Action. Under Action Details, select a platform type and then choose an action type from the dropdowns (see our Actions' Catalog for descriptions of action types). Name your new action and type a Description, then click Create.

Editing options for this action will depend on the type of action selected.

## Using Actions and Examples

This sections contains examples on how to configure and use actions in Privilege Manager.

These following topics are available:

* [Adjust Process Rights Action and use Unrestricted Token](unrestricted-token.md)
