[title]: # (Resource Service)
[tags]: # (Console and Internal Services)
[priority]: # (100) (edited) 
# ResourceService

## Path

/api/resource

## Description

Resource Targets are lists of resources (items of a few specific types, mostly agents) and this service contains the methods to evaluate and update them

## Methods

* GetResourceTargetsForItem – This method returns a list of resource targets which an item ID is a member of
* EvaluateResourceTargetsForItem – This method returns a list of ItemIDs for all resource targets which an item is a member of
* EvaluateResourceTarget – This method returns a list of ItemIds for a specific resource target
* EvaluateResourceTargetTotalCount – This method returns a count of items which match a specified resource target
* EvaluateResourceTargets– This method returns a list of ItemIds for a list of resource target
* GetResourceListReports – This method returns a report on resource targets
* GetResourceSummaryReports – This method returns a summary of resource targets and the count of members
* GetResourceDataClassReports – This method returns a report of the data classes for a resource target
* DiscloseUserPassword – This method returns the credential object for a local user password
* DisclosePlainTextPassword – This method returns the plaintext for a local user password
* GetScopedCollectionReports – This method returns a list of collections scoped to a specified resource target
* GetCollectionReports – This method returns a report on collections
* GetResource – This method returns the contract for a specified collection
* SetResourcePassword – This method saves a plaintext password to a credential object for a resource
* SetOpenIDClientSecret– This method saves a plaintext password to a credential object for an authentication provider