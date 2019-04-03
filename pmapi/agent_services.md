[title]: # (Agent Services)
[tags]: # (API,Agent,Services)
[priority]: # (100) (edited) 
# Agent Services

## AgentRegistrationV3

This service accepts a registration object signed by the agent and saves the agent registration to the database.  This is included for compatibility with Pre-10.5 agents

## AgentRegistrationV4 

This service accepts a registration object signed by the agent and saves the agent registration to the database.  It will only accept the registration if it includes a valid installCode or if the signature on the registration matches one saved in the database for that AgentID

## AgentReputationService

This service accepts a file hash value and reputation provider ID signed by an agent and returns the reputation status from that provider (this is used for Virustotal or Cylance integration)

## ClientItems

This service accepts a request signed by an Agent and will return a hash of all items relevant to that agent ID.  It will also accept an ItemID and return the most current version of the item.  This is included for compatibility with pre-10.5 agents

## ClientItems2

This service accepts a request signed by an Agent and will return a hash of all items relevant to that agent ID.  It will also accept an ItemID and return the most current version of the item.  It will only accept the requests if the signature on the registration matches one saved in the database for that AgentID

## SendEvent

This service accepts a bits upload of an event (inventory or application action) signed by an agent and saves it to the server for processing
