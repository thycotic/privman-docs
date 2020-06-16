[title]: # (Commandline)
[tags]: # (filter types)
[priority]: # (2)
# Commandline Filter

These filters will perform an exact, partial or regex match on the commandline of the process. Privilege Manager comes with default commandline filter types, which are all read-only, but can be copied to be customized.

This filter is available for both Windows and macOS systems.

## Search for Commandline Filters

1. Navigate to __Admin | Filters__.
1. In the search field for the __Type__ column enter commandline.

   ![Commandline Filter type search](../images/search-2.png "Commandline Filter type search")
1. Select a filter to view its details and/or use __Duplicate__ to customize the filter.

   ![Commandline Filter default example](images/command-line-filter.png "Commandline Filter default example")

   If you Duplicate (make a copy of an existing) filter, "rename" the filter and click __Create__.

   ![duplicate](images/command-line-filter-2.png "Commandline Filter duplicate")


## Create a new Commandline Type Filter

1. Navigate to __Admin | Filters__.
1. Click __Create Filter__.
1. On the New Filter page, select the platform. For this example, select __Windows__.
1. From the __Filter Type__ drop-down select __Commandline Filter__.
1. Enter a name and description and click __Create__.

   ![New Commandline Filter](images/create-new.png "Create a new commandline filter")
1. Customize the newly created filter.

   ![New Commandline Filter edit](images/customize.png "Customize the filter")

   1. Under __Settings__,
      1. Set the __Match Type__. This can be either an exact or partial match or specified as a regular expression.
      1. Enter the commandline to match.
1. Click __Save Changes__.

## Parameters

Commandline Filters have one section to set the parameters for the filter.

The __Match Type__ gives you the options:

* Exact Match
* Partial Match
* Regular expression

__Command Line__:

* This is the section where you enter in the given command parameters to pull up the file or action.

## Examples

A commandline filter examines the commandline (excluding the primary executable) and applies a pattern match (Exact, Partial or Regular Expression).

For example allowing /FlushDNS as a command for IPConfig.
