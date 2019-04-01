# ConfigurationService

## Path

/api/configuration

## Description

Like most other data storage system and user level configurations are stored as classes serialized in the database.  These methods allow us to retrieve specific configuration settings.

## Methods:

* GetSystemConfiguration – This method returns all system configuration objects
* GetRunningProductConfiguration – This method returns all configuration objects for the current product
* GetPackageInstallHistory – This method returns the version of installed Packages
* GetConfigurationValue – This method returns the value of a specified configuration key
* SetConfigurationValue – This method sets a value to a specified configuration key
* GetPreference – This method returns the value of a user level preference key
* SetPreference – This method sets the value of a user level preference key
* DeletePreference – This method deletes the value of a user level preference key returning things to the default
* SecretServerLocalRelativeUri – If connected to a Secret Server Installation this method returns the relative URI to SecretServer
* ValidateExternalUri – This method validates a TMS URI using the external name rather than localhost
* AuthenticationProviderItemId – This method returns the ID value for the authentication provider
* RecycleWebApplications – This method instructs the server to recycle all app pools
* PauseRecords – This method returns a list of times the server has been paused to go into maintenance mode
* Pause – This method instructs the server to pause task execution and go into maintenance mode
* Resume – This method instructs the server to resume task execution and end maintenance mode