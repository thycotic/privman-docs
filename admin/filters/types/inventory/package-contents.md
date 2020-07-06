[title]: # (Package Contents)
[tags]: # (filter types)
[priority]: # (2)
# Package Contents Filter

This type of filter identifies file inventory based on package contents. *No out-of-box filters exist in Privilege Manager for this type*.

![create](images/package/pack-1.png "New Package Contents Filter")

## Parameters

Once the filter is created the following settings can be viewed and/or edited:

* Data Source, (__do not edit__) this is the Package Contents Query.
* Package:

  * Parameters:

    * Scope by Organizational Group
    * Search text
    * Maximum rows returned, this is a required parameter and the default is 10000.
  * Select Resource, this is the actual package resource that has to be selected for the query.
* Results will be either excluded (default) or included.

![view](images/package/pack-2.png "The Package Contents Filter")

### Viewing and Editing the Package Parameters

![edit](images/msi/msi-pack-3.png "Edit the parameters of the Package Contents Filter")

### Adding the Resource(s)

![select](images/msi/msi-pack-4.png "Selecting the Resource for the Package Contents Filter")
