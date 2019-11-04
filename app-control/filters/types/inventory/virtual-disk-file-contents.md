[title]: # (Virtual Disk File Contents Filter)
[tags]: # (filter types)
[priority]: # (2)
# Virtual Disk File Contents Filter

The Virtual Disk File Contents Filter filters files contained in the specified virtual disk file. *No out-of-box filters exist in Privilege Manager for this type*.

![New Virtual Disk File Contents Filter](images/virtual-disk/file-1.png)

## Parameters

Once the filter is created the following settings can be edited:

* Data Source, (do not edit) this is the MSI File Contents Query.
* File:

  * Parameters (these are required)

    * Win32 Executable
    * Product Name
  * Select Resource, this is the actual MSI file resource that has to be selected for the scan.
* Results will be either excluded (default) or included.

![Edit the Virtual Disk File Contents Filter](images/virtual-disk/file-2.png)

### Viewing and Editing the Parameters

![Edit the parameters of the Virtual Disk File Contents Filter](images/virtual-disk/file-3.png)

### Viewing and Adding the Resource(s)

![Selecting the Virtual Disk Resource for the Virtual Disk File Contents Filter](images/virtual-disk/file-4.png)
