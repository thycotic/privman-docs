[title]: # (MSI Package Contents Filter)
[tags]: # (filter types)
[priority]: # (2)
# MSI Package Contents Filter

This type of filter identifies file inventory based on MSI package contents. *No out-of-box filters exist in Privilege Manager for this type*.

![New MSI Package Contents Filter](images/msi/msi-pack-1.png)

## Parameters

Once the filter is created the following settings can be edited:

* Data Source, (do not edit) this is the MSI Package Contents Query.
* Package:

  * Parameters:

    * Scope by Organizational Group
    * Search text
    * Maximum rows returned, this is a required parameter and the default is 10000.
  * Select Resource, this is the actual MSI package resource that has to be selected for the query.
* Results will be either excluded (default) or included.

![Edit the MSI Package Contents Filter](images/msi/msi-pack-2.png)

### Viewing and Editing the Parameters

![Edit the parameters of the MSI Package Contents Filter](images/msi/msi-pack-3.png)

### Viewing and Adding the Resource(s)

![Selecting the MSI Resource for the MSI Package Contents Filter](images/msi/msi-pack-4.png)
