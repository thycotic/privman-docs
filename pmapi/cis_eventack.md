[title]: # (Event Acknowledge Service)
[tags]: # (Console and Internal Services)
[priority]: # (100) (edited) 
# EventAckService

## Path

/api/eventack

## Description
Events reported to privilege manager through the agents can be viewed and acknowledged, either singly or as a group using this service

## Methods

* GetAck – This method returns an event acknowledgement
* GetSummaryAck – This method returns the summary for all events of a specific type
* GetAcks – This method returns a list of event acknowledgement
* GetSummaryAcks – This method returns the summary for all events types in a list
* AddAck – This method acknowledges an event
* AddSummaryAck – This method acknowledges all events of a specific type
* GetEventDetailsReport – This method returns the details of a specific event ID