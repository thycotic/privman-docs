[title]: # (Security Ratings)
[tags]: # (filter types)
[priority]: # (2)
# Security Rating Filter

If you have integrated Privilege Manager with a Reputation Checking provider like VirusTotal, these filters allow you to look up a rating for a file or application (is it good, bad, suspect/suspicious, or unknown).

![Security ratings filter](images/security-ratings-1.png "Create a security ratings filter")

This filter is available for both Windows and macOS systems.

## Parameters

![Security ratings filter](images/security-ratings-2.png "New security ratings filter")

The parameters for the Security Rating Filter would include the following:

* Security Rating System
  * Application Control Rating System
  * Cylance Rating System
  * VirusTotal Rating System  
* Rating level
  * Unknown
  * Clean
  * Suspect
  * Bad
* Timeout, can be specified in seconds or milliseconds
* Error Handling
  * On timeout, consider the result
    * Matched
    * Note Matched
    * Error Condition
  * On Failure, consider the result
    * Matched
    * Note Matched
    * Error Condition

## Examples

The example above displays how to create a security rating filter after integrating Privilege Manager with VirusTotal.
