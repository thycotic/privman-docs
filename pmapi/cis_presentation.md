[title]: # (Presentation Service)
[tags]: # (Console and Internal Services)
[priority]: # (100) 
# PresentationService

## Path

/api/presentation

## Description

Presentations are classes which control the look and feel of the privilege manager user interface.  They are used both in the newer Angular based console as well as the older Silverlight console and this service contains the methods to retrieve presentation objects associated with a specific item or type as well as constructing treeviews and context menus

## Methods

* GetPresentationForItem – This method returns the presentation for a specified item ID
* GetContextMenuForItem – This method returns the context menu presentation for an Item ID
* PerformAction – this method performs the action for a context menu ID and an Item ID
* GetTreeNodes – this method returns the tree nodes under an Item
* GetPresentation – This method returns the presentation by presentation ID
* GetTreeNodes2 – this method returns the tree nodes under an Item
* GetTreeNodesByRoleType – this method returns the tree nodes under a role type
* GetTreeNodesByRoleType2 – this method returns the tree nodes under a role type
* GetContextMenu – This method returns the contract for a context menu by ID
* GetContextMenuWithParameters – This menu returns the contracts for context menus for a set of supplied parameters
* GetContextMenuForCreatableItems – This method returns a list of contract items for all context menus that can create items
* GetContextMenuForCreatableItemsForFolder – This method returns a list of contract items for all context menus that can create items in a folder
* GetResourceTypeConsole – This method returns a list of all resource types applicable to a console ID
* GetScopeSetTreeFilterView – This method returns a filtered list of items under a specific tree node
* SetScopeSetFilters – This method sets the filters for a tree node