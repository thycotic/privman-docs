[title]: # (Gauge Service)
[tags]: # (Console and Internal Services)
[priority]: # (100) (edited) 
# GaugeService

## Path

/api/gauge

## Description

Gauges are specialized queries used to return specific values on a schedule.  Mostly used for reporting and notification each gauge instance contains an execution of the specified gauge query along with a state controlled by the gauge thresholds

## Methods

* GetCurrentSystemConfiguration – This method returns the configuration values for the current system
* SetSystemConfigurationType – This method sets a system configuration value
* GetGauge – This method returns the contract for a Gauge
* GetGaugeInstance – This method returns the details of a specific instance of a gauge
* GetNSMonitoredGaugeInstance – This method returns a list of monitored gauges in error state
* GetGaugesforMonitoredResource – This method returns all monitored gauges for a specific resource
* GetServerGaugeInstance – this method returns the details of specific server gauge
* GetGaugesbyType – this method returns the list of all IDs for gauges by typeID
* GetGaugesbyCategory – this method returns the list of all IDs for gauges for a category
* GetGaugeStates – this method returns the list of all IDs for gauges in a specified state (normal, warning, error, critical)
* UpdateServerGaugeState – this method instructs the server to update the state of a specified gauge generating a new instance