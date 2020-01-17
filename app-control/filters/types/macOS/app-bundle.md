[title]: # (App Bundle)
[tags]: # (filter types)
[priority]: # (3)
# App Bundle Filter

This type of filter identifies app bundles for macOS systems.

Prior to Privilege Manager 10.7.1, the value of the Bundle Name field requires the inclusion of the .app extension (e.g. Console.app). If it is not present, the filter will fail to properly match.

With Privilege Manager 10.7.1, the presence of the .app extension is properly calculated during policy processing.

![MacOS application bundle filter](images/app-bundle.png)

## Parameters

* Bundle Name
* Bundle Path

  * Include subdirectories

The following bundle properties can be used to identify an application bundle in an Application Bundle filter:

* App Category
* Bundle Identifier
* Bundle Name
* Bundle Version
* Bundle Version (short)
* Executable File
* Info String
* Min System Version
