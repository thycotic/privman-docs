[title]: # (Association Service)
[tags]: # (Console and Internal Services)
[priority]: # (100) 
# AssociationService

## Path

/api/associations

## Description

Associations control the links between items in Privilege Manager.  This service allows us to track them

## Methods

* GetDescriptiveAssociation – This method returns the full contract of the associationID provided in the parameters
* GetAssociationTypeIdsForRoles – This method returns the ID values for association types for the RoleID provided
* GetAssociationTypesForResource – This method returns the ID values for all association types for the Resource provided
* GetDataClassDescriptiveAssociations – This method returns the contracts of the associations for a data class
* GetAllDescriptiveAssociations – This method returns the contracts of all association types for the ItemID provided
* GetAssociationsMembersReport – This method gets the contracts of all the associations for a given AssociationTypeID
