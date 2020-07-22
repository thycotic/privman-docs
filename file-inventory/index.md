[title]: # (File Inventory)
[tags]: # (admin,configuration)
[priority]: # (4000)
# File Inventory

The file inventory page lists all files discovered based on the Basic Inventory policies. 

The table grid contains the following columns:

* File Name
* Original File Name
* Product Name
* Product Version
* First Discovered

![file inv](images/file-inv.png "File Inventory page")

At the beginning of your policy creation process you will see many new events labeled as __New Loaded Resource__. This is because importing files in Privilege Manager is not the same thing as discovering information about the files. Discovery of file details is done by scheduled tasks by default, but if you want to discover file details immediately, do the following:

1. Navigate to __File Inventory__.
1. Select __New Loaded Resource__.

   ![New Loaded Resource](images/new-loaded-resources.png "Inventoried files and new loaded resources")
1. Click one of the inventoried file or on a New Loaded Resource entry.
1. Click __View File__ or __Create Filter__ as your next option to use the discovered or inventoried resource. You have the option to create a filter and to add it to a Policy.

>**Note**:
>Files may not be discovered if they have already been deleted from your system.
