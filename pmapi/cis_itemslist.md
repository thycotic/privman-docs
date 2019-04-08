[title]: # (Item List Service)
[tags]: # (Console and Internal Services)
[priority]: # (100) 
# ItemsListService

## Path

/api/itemlist

## Description

The itemlist service is mostly used to hydrate contracts delivered by the item service as well as to interact with larger batches of items

## Methods

* GetDescriptiveItem – this method returns the full contract for an item
* GetDescriptiveItems – this method returns the full contract for a list of items
* GetDescriptiveItemsbyTag – this method returns the contracts for all items with a specified tag
* GetDecriptiveItemsbyRoleType  – this method returns the contracts for all items with a specified role type
* GetDecriptiveItemsbyRoleTypes – this method returns the contracts for all items with role type in the provided list
* GetDescriptiveItemsInFolder – this method returns the contracts for all items with a specified folder
* GetDescriptiveItemsbyRoleTypeAndProduct – this method returns the contracts for all items with a specified role type and product
* GetDescriptiveItemsbyRoleTypeAndProductAndFolder – this method returns the contracts for all items with a specified role type, product, and folder id
