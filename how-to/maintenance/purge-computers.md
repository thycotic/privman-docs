[title]: # (Purge Computers)
[tags]: # (maintenance)
[priority]: # (2)
# How to Purge Computers

After using Privilege Manager for a certain amount of time, you may have computers that haven't communicated with the Privilege Manager server for an extended period of time. This can be done via the Purge Computers task, which can be found under Configuration on the General tab.

1. Navigate to __Admin | Configuration__ and select the __General__ tab.
1. Under the Maintenance Settings section click __Purge Old Computers__.

   ![select](images/maintenance/purge-computers-1.png "Selecting the Purge Computers task")
1. On the __Purge Old Computers__ page select the __General SQL Executions__ tab.
1. Verify that __Query 1__ is set to __Purge Agent Gauge Data for Deleted Computers Query__.

   ![verify 1](images/maintenance/purge-computers-2.png "Query verification - General SQL Executions")

   If for whatever reason that specific query is not listed or if you need to add other queries,

   1. Click __Add__ to either replace the query currently listed or add this query.
   1. Start typing the query name _Purge Agent Gauge Data for Deleted Computers Query_ and select the query from the results list.

      ![add](images/maintenance/purge-computers-2a.png "Query verification - Add Query")
   1. Click __Save Changes__.
1. Select the Resource Purge SQL Executions tab.
1. Verify that __Query 1__ is set to __Managed Computers to Delete__.

   ![verify 2](images/maintenance/purge-computers-3.png "Query verification - Managed Computers to Delete")

   If that specific query is not listed,

   1. Click __Add__ to either replace the query currently listed or add this query.
   1. Start typing the query name _Managed Computers to Delete_ and select the query from the results list.
   1. Click __Save Changes__
1. Click __Show Parameters__. The Days field indicates after how many days a system is considered to be an old computer and thus should be purged. The default value is 90 days. If you want a different value, enter a number to change the number of days.

   ![adjust # of days](images/maintenance/purge-computers-4.png "Adjust the number of days, after which a computer is considered old")
   1. Click __Save Changes__.
1. Click __More | Run Task__.
1. On the __Task Name__ modal, you may change the task name and click __Run Task__.
1. On the __Task History__ tab you can view the status of the running task by selecting the task from the table grid.

   ![status](images/maintenance/purge-computers-5.png "View the status")
