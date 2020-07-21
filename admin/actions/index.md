[title]: # (Actions)
[tags]: # (overview)
[priority]: # (1)
# Actions

In Privilege Manager, taking action is the name of the Application Control game.
Once you know how to accurately identify events via filters, the next crucial step in policy creation is to make stuff happen by applying specific actions to your filtered targets. This begs the question: what actions are possible to perform in Privilege Manager?

The most popular and well-known action categories in Application Control include:

* __Blocking Actions__ - Blocking an application simply means: deny it, or prevent it from running.
* __Monitoring Actions__ - This is a category of actions that can be applied to unknown applications that attempt to run. Sandboxing is another term often linked to monitoring, because you can create policies that link to reputation checking tools (like VirusTotal) to perform smart actions once an unknown file’s reputation has been verified.
* __Elevation Actions__ - Allowing an application to run (allow listing) is good and well for trusted programs, but many trusted applications also require a higher credential set than your end users normally have access to. The elevation action category will allow an application to run with elevated permissions so any user can, for example, install that trusted HP printer on your network without taking time out of a HelpDesk employee’s day. Implementing elevation policies allow "Least Privilege" to be implemented by your organization, eliminating the need for local users to have full administrator access on their computer.
* __Workflow Actions__ - Some actions explicitly enforce an organization's workflow system. The big example here is the “Request Access” action that will prompt a user for the reason they are trying to access an application for verification purposes and auditing.
* __Display Message Actions__ - Display messages are paired with one of the action types listed above. Display Message Actions are customizable and serve to tell the end user what is happening and why.

For a more complete (and more specific) list of all out-of-the-box Privilege Manager actions and types of actions, see the [List of Default Actions](default-actions.md) topic.

## Creating a New Action Manually

Navigate to __Admin | Actions__ in Privilege Manager and click __Create Action__. Under Action Details, select a platform type and then choose an action type from the dropdowns (see our Actions' Catalog for descriptions of action types).

![create](images/action-both-new-2.png "Create Action dialog")

Select a specific platform or choose both:

![platform](images/action-both-new-1.png "Select Platform")

If __Both Windows / Mac OS__ is selected, enter a name/description and click __Create__. Otherwise select a type from the drop-down based on selected platform:

* Windows:

  ![Create a new Action - Windows](images/new-action.png)
* macOS:

  ![Create a new Action - macOS](images/new-action-macOS.png)

Name your new action and type a Description, then click __Create__.

Editing options for this action will depend on the type of was action selected from the drop-down.

![new action](images/action-both-new.png "Newly created action")