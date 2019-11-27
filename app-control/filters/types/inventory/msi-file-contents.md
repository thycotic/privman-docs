[title]: # (MSI File Contents)
[tags]: # (filter types)
[priority]: # (2)
# MSI File Contents Filter

This type of filter identifies file inventory based on .MSI file contents, i.e. specific Windows package installers. *No out-of-box filters exist in Privilege Manager for this type*.

![New MSI File Contents Filter](images/msi/msi-file-1.png)

## Parameters

Once the filter is created the following settings can be edited:

* Data Source, (do not edit) this is the MSI File Contents Query.
* File:

  * Parameters (these are required)

    * Win32 Executable
    * Product Name
  * Select Resource, this is the actual MSI file resource that has to be selected for the scan.
* Results will be either excluded (default) or included.

![Edit the MSI File Contents Filter](images/msi/msi-file-2.png)

### Viewing and Editing the Parameters

![Edit the parameters of the MSI File Contents Filter](images/msi/msi-file-3.png)

### Viewing and Adding the Resource(s)

![Selecting the MSI Resource for the MSI File Contents Filter](images/msi/msi-file-4.png)
