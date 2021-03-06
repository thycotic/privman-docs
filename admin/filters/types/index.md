[title]: # (Filter Types)
[tags]: # (description, overview)
[priority]: # (5000)
# Filter Types and Descriptions

There are different types of filters for different operating systems and applicable functional areas. When creating a new filter,

* the __Platform__ drop-down offers a choice of macOS, Windows, and Unix/Linux.

  * [Unix/Linux](nix/index.md)
  * [Mac OS](macOS/index.md)
  * Windows

* when Windows or macOS is selected as a platform, the __Filter Type__ drop-down gives a list of options based on that platform selection:

  * [Application Filters](application/index.md)
  * [File Filters](file/index.md)
  * [Inventory Filters](inventory/index.md)

These are loose groupings that signify a few different approaches to the filtering method or targets.

## Common Filter Characteristics

Each filter has a Details area that contains the filter name, description, and platform association. These details are usually specified when you create the filter, either by choosing __Create Filter__, editing an existing filter, or duplicating an existing filter.

Those characteristics are used for searches or filtering and allow users to easily find existing filters.

### Filter Change History

Each filter has a __Change History__ tab, where audit information can be reviewed from the time the filter was created in the system.

![filter change history](images/history.png "Filter Change History tab information")

Refer to [Change History](../../config/history/index.md) to learn more about drilling down into the change history of resources and the report.

## How to Search for Filters

All out-of-the-box filters can be searched, duplicated, and then customized to be used in policies.

1. Navigate to __Admin | Filters__.

   ![list](images/list.png "List of filters")

   The list of all filters is sortable by Name (default), Description, Type, and OS Support.

   You may limit your list output, by changing from the default __All__ or Supported selection for macOS or Windows to Not Supported. 

   ![search](images/search.png "Output and search option for filters")
1. Using the search option next to the OS drop-down, lets you search the list contents based on the column the contents is sorted by. So if your list is sorted by __Name__, but you are looking for all commandline filter types you have in the system, sort your list by __Type__ first.
1. Then click __Search__ and enter a search term, for this example _commandline_.

   ![search 2](images/search-2.png "Search output by type commandline filter")

You can also use the search option on the top-right from any page of your Privilege Manager console and get the a list of commandline filters returned. If you use this search option, the search field does not retain your search term. The results are based on the search term matching the Name and/or Type, so the list will contain more items than searching based on column selection.

![search 3](images/search-3.png "Search output without column selection")

The columns returned for this search are sorted by Name (default), Type, Modified Date, and Description.
