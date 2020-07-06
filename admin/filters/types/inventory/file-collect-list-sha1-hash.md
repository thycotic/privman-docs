[title]: # (File Collection from List of Sha1 Hashes)
[tags]: # (filter types)
[priority]: # (2)
# File Collection from List of Sha1 Hashes Filter

This type of filter identifies file inventory based on Secure Hash Algorithms. *No out-of-box filters exist in Privilege Manager for this type*.

When creating this filter the target hashes need to be entered as a comma-separated list:

![create](images/sha1/new-sha1.png "New SHA1 Hashes filter")

This filter is available for both Windows and macOS systems.

## Parameters

Once the filter is created, the following settings can be viewed and/or edited:

* Data Source:

  * Hash Based Query (__do not change the data source__)
* Results will be:

  * Included (default)
  * Excluded

![view](images/sha1/sha1-edit-1.png "Settings for the SHA1 Hashes filter")

Under the __Membership__ tab various reports can be viewed:

* All Files Picker Report
* Win32 File Picker Report
* Default Resource Picker Report

![edit](images/sha1/sha1-edit-2.png "Membership tab showing All Files Picker Report by default")

Under the __Related Items__ tab items will be listed if the filter is used in a policy or as a secondary filter.
