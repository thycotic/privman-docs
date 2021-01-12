[title]: # (Package Verification)
[tags]: # (checksums)
[priority]: # (1700)

# Package Checksum Verification

Privilege Manager verifies the checksums of downloaded packages during the install/update process.

The following measures are implemented:

* Privilege Manager prevents zero byte files from being stored on disk. It reconsiders any corrupted files as they are detected and renames/removes/deletes those.
* Privilege Manager ensures any download or disk write failures (disk space issues, rights, etc) do not leave remnants of partially extracted packages on the system.
* For offline package installs, Privilege Manager assumes the user has validated the package integrity. Refer to __Validating Package Integrity__ below.
* Privilege Manager writes a warning into the logs.

Any tempering or disk-write failure are logged, for example skipping package validation if the checksum cannot be received from the NuGet server, or for offline updates or packages that are considered pre-release and not yet publicly available.

## Validating Package Integrity

Locally on your system, set the NuGet repository URL in the web.config file to the local repo address at `c:\ProgramData\NuGetCache. Privilege Manager checks each file to see if there is a corresponding file with .hash.json extension. This json file contains the HashBase64 and HashAlgorithm property value pairs.
