[title]: # (Worker Service)
[tags]: # (Console and Internal Services)
[priority]: # (100) (edited) 
# WorkerService

## Path

api/worker

## Description

This service allows us to interact with the worker application pool which handles task execution.  Because tasks can be intermittent based on their schedule this pool can go to sleep and the ping allows us to ensure that it is awake and taking tasks

## Methods

* Ping – This method pings the worker pool to wake it up if it has gone to sleep