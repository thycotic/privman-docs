[title]: # (Task Service)
[tags]: # (Console and Internal Services)
[priority]: # (100) (edited) 
# TaskService

## Path

/api/task

## Description

Tasks in privilege manager are regularly scheduled activities.  Each time a task schedule fires it generates a task instance which performs the specified action according to its parameters.  This service contains the methods to fire tasks as well as interact and check the status of running task instances or their history

## Methods

* ExecuteTask – This method generates a task instance for a task
* TerminateTask – This method ends a running task instance
* GetExecutionInstance – This method returns a specific instance for a task
* GetExecutionInstances – This method returns all instances for a specific task
* GetRunningExecutionInstances – This method returns all currently running task instances
* WakeTaskInstance – This method wakes a sleeping task instance
* WakeIncompleteInstancesForTask – This method wakes all incomplete instances for a task
* GetTaskSchedulesForTask – This method returns the schedule for a task
* RunTaskScheduleNow – This method evaluates a schedule and generates a task instance if it is due
* StartTaskExecutionInstancesNow – This method immediately starts a task instance for a task
* StopTaskExecutionInstances – This method stops all task instances for a task
* DeleteTaskExecutionInstances – This method deletes a task instance
* GetChildTaskExecutionInstances – This method gets all child tasks of a given task instance
* GetTaskParameters – This method returns the parameters for a given task instance
* GetTrackedActivities – This method returns all activities for a specified task instance
* GetActivityEvents – This method returns all events for an activity