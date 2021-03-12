[title]: # (Resource Explorer)
[tags]: # (details)
[priority]: # (12)
# Resource Explorer

The Resource Explorer provides information about any type of resource item in Privilege Manager.

The Resource Explorer provides:

* __Summary__, which contains general information, such as name, description, and modified date for any resource accessed.
* __Known Data__, such as any data known that relates to the resource. This data is different from resource type to resource type. For example, a domain has Global Domain Details and no account details, and a file will have all sorts of information pertaining to the file.
* __Events__ are log-style data entries that are directly related to the resource. For example for discovered files, those are the events that are reported from and endpoint.
* __Associations__, are any associated/related items.

Resources can be deleted from the Resource Explorer page.

>**Note**:
>Only use Delete when you are absolutely sure that you want to delete that resource. Clicking on Delete will delete the current resource record you are viewing.

The Resource Explorer is accessible by either navigating to

* __Admin | Resources__ and expanding the Resources tree drilling down to a named resource to further explore and/or edit.

  ![Opening Resource Explorer via items in Resources tree](images/resource-explorer/resources-tree.png "Opening Resource Explorer via items in Resources tree")

* __Change History__ tab of a named resource.

  ![Opening Resource Explorer via the Change History tab](images/resource-explorer/change-hi-tab-details.png "Opening Resource Explorer via the Change History tab")

* any named item, such as a report, in the Privilege Manager console and selecting a named resource. Example navigation for the following image, _Admin | Agents | select one system from the list | select one computer from "Managed Computers by Operating System
​" list_:

  ![Opening Resource Explorer via other console areas](images/resource-explorer/named-resource.png)

## Example for Discovered Files

You enter the Resource Explorer for discovered file through __File Inventory__ on the main navigation tree. On the Events page, click any of the discovered files and use __View File__ to drill down to the files resources.

The following image shows all discovered information about the chrome.exe file, such as:

* File Name
* Original File Name
* Product Name
* Version
* Internal Name
* Company Name
* Copyright information
* File Hashes
* View Reputation, if a reputation provider is integrated with your Privilege Manager instance.

![inventoried file](images/resource-explorer/file-disc1.png "Resource Explorer for a Discovered File (Computer Locations): chrome.exe")

Under the __Reports__ drop-down you can look at further details on the __Computer Locations__, __Policy Events__, and __Similar Tiles Report__ tabs.

![reports](images/resource-explorer/reports.png "Reports drop-down")

The __Computer Locations__ tab provides details about the discovery locations where the file was discovered.

The __Policy Events__ tab provides details about the policy events that triggered by the file if executed.

The __Similar Files Report__ tab provides a list of and links to similar files that have been discovered by Privilege Manager.

![similar files](images/resource-explorer/file-disc2.png "Resource Explorer for a Discovered File (Similar Files): chrome.exe")

The Known Data for a discovered file includes details like the 

* File Inventory, which provides COFF Header and File Digital Signature data in raw form.

  ![coff](images/resource-explorer/file-disc-known-data1.png "Known Data Example - File Inventory | COFF Header information")

* Software Management, which provides the files Manifest, Version Info in raw form, and Win32 Executables details.

  ![win32](images/resource-explorer/file-disc-known-data2.png "Known Data Example - File Inventory | Win32 Executable information")

* File Details, such as name, file extension, file size, and if protected or not.
* File Digital Signature, which provided information on the Signer, Countersigner if available, and the signature date/time stamp.
* Hash, provides details on the name, the hash, and hex hash.

Under Events, Infrastructure offers a view into the Resource Discovery events that discovered the file, in this example the File Agent Discoverer and File Agent Discoverer (File Location) events.
![events](images/resource-explorer/file-disc-events.png "Known Data Example - Events")

This discovered file resource has no related items associated and thus the Associations area of the Resource Explorer is empty.

## Example for User Resource

When you are looking at change history for any item and click the view user link, you access the __Resource Explorer__ for that specific user resource. The Summary information for that specific user resources shows:

* Name – this is the user account that made the change.
* Created – indicates when the item was created.
* Modified – indicates when the item was last modified.

![select user](images/resource-explorer/select-user.png "Select the User link to learn more")

The resource explorer is providing information about the current state of that user resource.

![summary](images/resource-explorer/summary.png "Resource Explorer Summary")

Under __Known Data__ we can explore the information for __Security Management | Global Account Details__.

![Known Data](images/resource-explorer/known-data.png "Known Data")

Users can select the View from the drop-down and see information on the type of the resource. User resources provide details about:

* AccountDomain – identifies the domain for the user account.
* Description
* IsBuiltin – can be true false to indicate if the account in built-in or not.
* Name – Name associated with the user account.
* Rid
* SID

Selecting the Global Windows Users information shows Name, Domain, and UserId.

Under __Events__, you can view __Infrastructure | Resource Discovery__
information:

![Events](images/resource-explorer/events.png "Information about Resource Discovery Events")

Under __Associations__ you can see related items, such as __Group Membership__, which is based on the users credentials.

## Error Message after Deleting a User Resource

In case a resource was deleted, an error message like the following will be shown the next time the resource view link is accessed.

![Invalid Item Id Exception message](images/resource-explorer/invalidItemIdException.png)
