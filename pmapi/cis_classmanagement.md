[title]: # (Class Management Service)
[tags]: # (Console and Internal Services)
[priority]: # (100) 
# ClassManagementService

## Path

/api/class

## Description

Much of Privilege Manager's data is stored in XML which we serialize and deserialize into objects.  This service allows us to match up the contracts for registered classes and assemblies.

## Methods

* GetRegisteredClass – This method returns the contract for a registered class
* GetRegisteredClasses – This method returns contracts for a list of registered classes
* GetRegisteredClassByInterface – This method returns the contracts for all registered classes for an interface
* GetRegisteredClassByBaseClass – This method returns the contracts for all registered classes which inherit from a given base class
* GetRegisteredAssemblies – This method returns a list of all registered assemblies
* GetRegisteredSerializationAssemblies – This method returns a list of all registered assemblies which are marked for serialization.
