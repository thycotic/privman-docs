[title]: # (Data Class Service)
[tags]: # (Console and Internal Services)
[priority]: # (100) (edited) 
# DataClassService

## Path

/api/dataclass

## Description

Many items in Privilege Manager have associated data classes, small objects which hold specific types of data.  These methods allow for interaction with the dataclasses associated with an item or role

## Methods

* GetDataClassesForRoles – This method returns the data class contracts for a given list of role IDs
* GetDataClassData – This method returns the data class contracts for a given data class Id value
* GetDataClassesData – This method returns the contract and values for a given data class
* GetDataClassIdsHavingData – This method returns all data class IDs that match a given value
* GetDataClassesHavingData – This method returns the contracts for all data classes which match a given value