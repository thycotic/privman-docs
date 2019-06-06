[title]: # (Secondary File Filter)
[tags]: # (policy, deny, allow)
[priority]: # (4100)
# Secondary File Filter

Implementing a policy to prevent specific types of files from running on an endpoint is done by setting up a Secondary File Filter.

This article explains the steps for creating filters and policies to enforce actions on endpoints when either a batch file, powershell script, or msi file is run.

In general the steps are similar for different type of files to be policed. You first create a file filter identifying the file type and then you create a policy, which uses that filter.

## Batch File

## Powershell Script

## MSI 


### RegEx Examples

program name with version in file name:
```(flashutil[ a-zA-Z0-9\.]+exe)```
winamp58_3660_beta_full_en-us
```(winamp[ a-zA-Z0-9\.]+exe)```
Wireshark-win64-2.6.6.exe
```(wireshark-win64-[ a-zA-Z0-9\.]+exe)```