[title]: # (Using RegEx)
[tags]: # (policy)
[priority]: # (10)
# Using RegEx in Policies and Filters

Various Privilege Manager policies and filters use Regular Expressions (RegEx) to specify application or file names to match against.

For Privilege Manager all RegEx strings need to be in lowercase. A good resource for testing RegEx is https://regexr.com

## Special RegEx Characters

The following characters have special meaning in RegEx, and should be used with an escape character when there is a need to represent a literal character.

To perform the escape a \ (backslash) needs to precede the following characters: __+ * ? ^ $ . [ ] { } ( ) | \ /__

A Privilege Manager Win32 file filters path name does not use the ending directory slash `\`. RegEx for path names should also not include the ending `\`

### Escape Example

For the literal `(x86)\.net\C++` the RegEx is `\(x86\)\\\.net\\c\+\+`.

### Wildcard Example

In RegEx: `.*` is a wildcard

## File Name Examples

### Match with Wildcard before the File Name

Matching anything before the file name and ending with a file type, use a wildcard before the file name.

`File Name="*eetechcode.exe"` use this in Privilege Manager `(.*eetechcode\.exe$)` 

Results:

* Match eetechcode.exe
* NoMatch eetecTesThcode.exe
* NoMatch eetechcodeTesT.exe
* Match TesTeetechcode.exe

### Match File Name Containing String and File Type

To match a filename that contains a character string on both sides of the actual file name and that must end with a specific file type:

`File Name="*eetechcode*.exe"` use this in Privilege Manager `(.*eetechcode.*\.exe$)`

Results:

* Match eetechcode.exe
* NoMatch eetecTesThcode.exe
* Match eetechcodeTesT.exe
* Match TesTeetechcode.exe

### Match with Wildcard at end of File Name and before File Type

Matching a file name with a string that contains anything between the string and the file type.

`File Name="eetechcode*.exe"` use this in Privilege Manager `(^eetechcode.*\.exe$)` this is a 

Results:

* Match eetechcode.exe
* NoMatch eetecTesThcode.exe
* Match eetechcodeTesT.exe
* NoMatch TesTeetechcode.exe

### Match with Wildcard in the Middle of Two Strings

Matching a file name beginning with a sting, followed by a wildcard and another string with the last string that includes the file type at the end.

`File Name="eetech*code.exe"` use this in Privilege Manager `(^eetech.*code\.exe$)`

Results:

* Match eetechcode.exe
* Match eetecTesThcode.exe
* NoMatch eetechcodeTesT.exe
* NoMatch TesTeetechcode.exe

### Match with Wildcard at End of File Type

Matching a file name with the wildcard at the end of the file name after the file type, when the filename begins with a string that includes the file type and matches anything after the file type. 

`File Name="eetechcode.exe*"` use this `(^eetechcode\.exe.*)` 

Results:

* Match eetechcode.exe
* NoMatch eetecTesThcode.exe
* NoMatch eetechcodeTesT.exe
* NoMatch TesTeetechcode.exe

## File Path Examples

### Wildcard at the End of the Path

To match when a wildcard is at the end of the File Path like:

`File Path="C:\Program Files\Thycotic\Agents\Agent\*"` use this `(^c:\\program files\\thycotic\\agents\\agent.*)` 

>**Note**:
>The final backslash has been removed for Privilege Manager.

Also note the system variables like `%ProgramFiles%` don’t work using regex unless `%ProgramFiles%` is what is shown in the Privilege Manager logs for the event.

Results:

* Match C:\Program Files\Thycotic\Agents\Agent
* NoMatch \Program Files\Thycotic\Agents\Agent
* NoMatch %ProgramFiles%\Program Files\Thycotic\Agents\Agent
* Match C:\Program Files\Thycotic\Agents\Agent\x86

### Wildcard in IP Address for Network File Path

To match when a wildcard is used in an IP address for a network File Path like:

`File Path="\\10.10.10.*\Program Files\Thycotic\Agents\Agent"` use this `(^\\\\10\.10\.10\..*\\program files\\thycotic\\agents\\agent$)` 

>**Note**:
>The final backslash has been removed for Privilege Manager.

Results:

* No Match C:\Program Files\Thycotic\Agents\Agent
* NoMatch \Program Files\Thycotic\Agents\Agent
* NoMatch %ProgramFiles%\Program Files\Thycotic\Agents\Agent
* NoMatch C:\Program Files\Thycotic\Agents\Agent\x86
* Match \\10.10.10.2\ProgramFiles\Thycotic\Agents\Agent
* Match \\10.10.10.9\ProgramFiles\Thycotic\Agents\Agent

### Wildcard for Application Updates for all Users

To match when a wildcard is used several times to target application updates for all Users:

`File Path ”*\Users\*\AppData\Local\Temp\notepad++\*\bin"` use this `(.*\\users\\.*\\appdata\\local\\temp\\notepad\+\+\\.*\\bin$)`

This targets any drive, any user, and multiple versions of an application update. Building filters like these can help streamline Privilege Manager administration since the filter stays current even with new versions coming out and working for all users. 

Results:

* Match C:\Users\MarkH\AppData\Local\Temp\notepad++\1.23.59874\bin
* Match C:\Users\DarinS\AppData\Local\Temp\notepad++\1.23.59874\bin
* Match C:\Users\MarkH\AppData\Local\Temp\notepad++\2.56.89457\bin
* Match C:\Users\DarinS\AppData\Local\Temp\notepad++\2.56.89457\bin
* NoMatch C:\Users\MarkH\AppData\Local\Temp\notepad++\2.56.89457
* NoMatch C:\Users\MarkH\AppData\Local\Temp\notepad++\2.56.89457\bin\test
