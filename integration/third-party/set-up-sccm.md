[title]: # (Set-up SCCM Integration)
[tags]: # (integration)
[priority]: # (9101)
# Set-up SCCM Integration

Privilege Manager can import Collections and package data from Microsoft SCCM.  The collections can then be used to target computers in policies, and the package data used to create application filters. This integration allows users to deploy changes in Privilege Manager across large environments quickly and effectively.

## Connecting to SCCM

Before you can import data from SCCM you need to setup a foreign system connection in Privilege Manager for the SCCM integration.

## Create a Credential

Privilege Manager needs a username and password to access SCCM.  If you have not already created an appropriate user credential, navigate to Privilege Manager's Legacy Silver Light Console, to the Configuration tab, then to Settings > Foreign Software Systems > User Credentials.  Click New > User Credential, fill out the form and Save.

User-added image

## Add the SCCM Instance

Next Privilege Manager needs to know how to connect to SCCM.  Navigate to the Configuration tab, then in the tree to Settings > Foreign Software Systems > System Center Configuration Manager.  Click New > SCCM Instance.  Fill out the required fields and select OK.

User-added image

Next you need to select the user credential you created for accessing SCCM.  Select your credential, click OK, and then Save to save the SCCM information.

User-added image

## Import Computers from SCCM

Before you can import collection data from SCCM, Privilege Manager needs to know about computers in your SCCM.  Navigate to the Tasks tab > Jobs and Tasks, then in the tree to Jobs and Tasks > Server Tasks > Foreign Systems > SCCM > Synchronize Computers.  Click Run Now, then click Select to choose your SCCM, click OK, then Run Task.

User-added image

> **Note**: You can also right-click on your SCCM from the Foreign Software Systems view and select Synchronize Computers to launch this task.

Next, verify the computers have been imported.  Navigate to the Resources tab > Resource section, then in the tree to Organizational Views > Default > All Resources > Asset > Network Resource > Computer.  Verify that the required computers have been imported.

User-added image

You can also verify that the computer resource you're viewing is connected to SCCM.  In the Computer view, right-click on a computer and select Resource Manager.  In the Resource Manager view, go to the Data tab, then in the tree to Data Classes > Foreign Systems.  You should have Foreign System Id and SCCM Platform Id data.

User-added image

## Create a Collection from SCCM

After computers have been imported, you can create a collection to mirror an SCCM collection.  Navigate to the Resource tab, Resource Filters section, then in the tree Resource Filters > Collections > Thycotic.  Right-click on the Thycotic folder then select New > Filters > SCCM Collection

User-added image

Fill out a Name and Description, select your SCCM instance, and select OK to create.

User-added image

Select the SCCM collection you want to mirror and then Save the collection.

User-added image

## Updating an SCCM Collection

Privilege Manager needs to pull the list of computers that are part of a collection from SCCM.  By default it will only do this on demand.  Go to the Tasks tab, Jobs and Tasks section, then in the tree Jobs And Tasks > Server Tasks > Foreign Systems > SCCM > Synchronize SCCM Collection.  Click Run Now, select your collection, and then Run Task to run the task.

User-added image

> **Note**: You can also run this task by right-clicking the collection in the tree and selecting Synchronize Collection.
>
>If you would like this to run automatically, you can setup a schedule to run by clicking the New Schedule button.  Select the collection, set schedule information, and Save.

User-added image

Next, navigate back to your SCCM Collection in Resources.  Click the Update Membership button to view the current members of the collection.

User-added image

> **Note**: It is also necessary for the Collection Update task to run, and this task is already scheduled by default for every 15 minutes. Clicking Update Membership will immediately perform the same actions as the Collection Update task.