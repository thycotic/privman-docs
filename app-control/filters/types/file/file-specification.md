[title]: # (File Specification)
[tags]: # (filter types)
[priority]: # (2)
# File Specification Filter

This filter identifies files based on their file path, or location on a computer.

![file specification filter](images/fs_1.png)

This filter is available for both Windows and macOS systems. Use this filter for macOS endpoints only to target known scripts or command-line tools; otherwise use the [Default File Specification (macOS)](../macOS/file-specification.md) filter.

>**Important**:
>On macOS 10.15 (Catalina) use the new preference pane specific filters to target macOS preference panes.
<!-- The File Specification Filter definition does not work on macOS 10.15 (Catalina) when the File Names field starts with "com.apple.preference" and/or Path field starts with "/System/Library/PreferencePanes/". Any Policies leveraging these filter definitions are also impacted. -->

## Example

1. Navigate to __Admin | More…__ and select __Filters__.
1. In the search field for the __Type__ column enter file specification filter.

   ![file specification filter](images/fs_2.png)
1. Select a filter to view its details and/or create a copy to customize the filter.

   ![file specification filter](images/fs_3.png)
1. Click __Edit__.
1. Set the needed parameters.

   ![file specification filter](images/fs_5.png)
1. Click __Save__.
