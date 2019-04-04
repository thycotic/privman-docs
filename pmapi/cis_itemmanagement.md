[title]: # (Item Management Service)
[tags]: # (Console and Internal Services)
[priority]: # (100) 
# ItemManagementService

## Path

/api/item

## Description

Items are the root level object inside of Privilege Manager and at their core just about everything is an item.  This service contains the methods for CRUD actions at the item level

## Methods

* GetItem – This method returns the contract for an item by ID
* GetItems – This method returns the contracts for a list of item IDs
* GetItemXml – This method returns the XML for an Item by ID
* SaveItem – This method takes an item contract and saves it
* SaveItemXml – This method takes an item XML and saves the item
* SaveItems – This method takes an array of item contracts and saves them
* DeleteItem – This method deletes an Item by ID
* DeleteItems – This method deletes a list of Items by ID
* CheckItemExists – This method returns a Boolean if the ItemID exists
* CloneItem – This method clones a specified item
* CreateItem – This method creates a new item from a template
* CreateItemTemplate – This method creates a new item template
* CreateItemByRoleType – This method creates a new item of a specified role type
* ExportItem – This method returns a string value representing an item
* SetNameAndDescription – This method updates the name and description for an item 
* MoveItemtoFolder – This method updates the Folder of a specified item
* MoveItemstoFolder – This method updates the Folder of a list of items
* GetItemProperties – this method returns the property-bag for an item
* GetItemsbyRoleType – This method returns all itemId values for a given role type
* GetItemsbyRoleTypeAndProduct – This method returns all itemId values for a given role type and product
* GetItemsByRoleTypeAndProductAndFolder – This method returns all itemId values for a given role type, product and that have a specified folder Id
* ImportItem – This method imports an item from XML
* ImportItemIntoFolder – This method imports an item from XML and overrides the folderID with a specified value
* AlterItemEnabled – this method sets the enabled flag for an Item
* AlterItemsEnabled – This method sets the enabled flag for a list of items
