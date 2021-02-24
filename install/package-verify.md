[title]: # (Package Hash Verification)
[tags]: # (checksums,sha512)
[priority]: # (1700)

# Package Hash Verification

## Automatically when Online

Privilege Manager verifies the SHA512 hash of downloaded packages during the install/update process. Installation of packages does not happen if a downloaded package hash does not match with the NuGet server information.

The following measures are implemented:

* Privilege Manager prevents zero byte files from passing hash validation.
* Through hash validation, Privilege Manager ensures any download or disk write failures (disk space issues, rights, etc) do not leave remnants of partially extracted packages on the system.
* Privilege Manager writes a warning into the logs and does not start an install/upgrade from the install pages unless it can validate the packages. It re-checks when the install is running, to accommodate other Privilege Manager servers in a multi-server environment, so that each server checks packages while doing its install.

Tempering or disk-write failures are logged, those can be due to skipped package validation, when the hash cannot be received from the NuGet server, or for offline updates or packages that are considered pre-release and not yet publicly available. Also, files shares can be setup, restricting a user's write access to prevent tempering of downloaded packages, which is a best practice for offline environments.

>**Note**: For offline package installs, Privilege Manager assumes the user has validated the package integrity. Refer to __Validating Package Integrity for Offline Upgrades__ below.

## Validating Package Integrity for Offline Upgrades

Privilege Manager does not verify package integrity in offline scenarios without the following user action. Users need to either

* copy the package hash files along with the NuGet packages, or
* calculate the hash files themselves (see PowerShell examples below.

If a hash file isn't provided, integrity won't be validated and a warning will be logged.

Locally on your system, set the NuGet repository URL in the `web.config` file to the local repo address at `c:\ProgramData\NuGetCache`. Privilege Manager checks each file to see if there is a corresponding file with `.hash.json` extension. This json file contains the HashBase64 and HashAlgorithm property value pairs to verify integrity.

Example from `ThycoticTmsCoreProduct11.0.1035.nupkg.hash.json`:

```json
{ "HashBase64": "CXs8cQ+65r6YWPpfylQVWdE4jHD3BhkJHlnWykAx1iItpcKmYhx6mkof/haChlu6aH8M+gYXUEN2ErH8wOPPlg==", "HashAlgorithm": "SHA512" }
```

Sample PowerShell script to calculate the hash for a package:

```powershell
$fileName = 'C:\ProgramData\NugetCache\ThycoticTmsCoreProduct.11.0.1040.nupkg'

$content = [System.IO.File]::ReadAllBytes($fileName)

$sha = [System.Security.Cryptography.SHA512]::Create()
$hash = $sha.ComputeHash($content)
$sha.Dispose()

$hashBase64 = [System.Convert]::ToBase64String($hash)

$hashBase64
```

Sample PowerShell script to take the NuGet package path and write an updated hash file:

```powershell
#
# Usage: UpdateNuGetHash.ps1 -NuGetFileName C:\ProgramData\NuGetCache\ThycoticTmsCoreProduct.11.0.1040.nupkg
#
param([Parameter(Mandatory=$true)][string]$NuGetFileName)

$content = [System.IO.File]::ReadAllBytes($NuGetFileName)

$sha = [System.Security.Cryptography.SHA512]::Create()
$hash = $sha.ComputeHash($content)
$sha.Dispose()

$hashBase64 = [System.Convert]::ToBase64String($hash)

$hashFileName = "$($NuGetFileName).hash.json"
$hashFileContent = "{ ""HashBase64"": ""$($hashBase64)"", ""HashAlgorithm"": ""SHA512"" }"

[System.IO.File]::WriteAllText($hashFileName, $hashFileContent, [System.Text.Encoding]::ASCII)

Write-Host "Updated hash file ""$($hashFileName)"" for nuget package ""$($NuGetFileName)""."
```