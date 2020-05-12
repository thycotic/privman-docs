[title]: # (Tasks)
[tags]: # (intro)
[priority]: # (6000)
# Tasks

In Privilege Manager tasks are activities that can be run on demand or regularly scheduled. If they are regularly scheduled, the schedule triggers the execution of a task instance, which performs specific actions based on set parameters.

Remote Scheduled Client Command type tasks that are considered agent-side require policies to be applied on the agent endpoints, the ones that are considered server-side do not require policies to be executed.

Tasks are set-up via __Admin | More__ and then selecting the Tasks link. They are categorized as following:

* [Client Tasks](client/index.md)
* [Server Tasks](server/index.md)
* [HelpDesk Tasks](helpdesk/index.md)
* [Infrastructure Scheduled Activities](infra-structure/index.md)

The following general task topics are available:

* [Agent Hardening](../install/agents/agent-hardening.md)
* [Maintenance tasks details](maintenance.md)
* [Other tasks to schedule](scheduled/index.md)
  
  * [Emailing Reports](scheduled/email-reports.md)
* [Reset Licensing](reset-license.md)
* [Tasks Launching Executables without User Context](launching-exe.md)

>**Note**: Upgrading to Privilege Manager 10.8 causes a task to run to merge computer groups and remove unused system computer groups. This primarily affects the Application Control policies that are using resource targets/computer groups named __All Windows Computers with Application Control Agent Installed__.  With 10.8, those policies will use the __Windows Computers__ computer group and macOS will use __MacOS Computers__.
>
>If you want to prevent this automatic merge, modify the XML of this item:
>
>`PrivilegeManager/#/item/xml/b2e02684-d154-48ca-9987-12b1759df822`
>
>Add on line 2 `<adc:Attributes>NoModify</adc:Attributes>`.
