[title]: # (Item Encryption)
[tags]: # (10.5+ new behavior)
[priority]: # (299)
# Item Encryption

With version 10.5+, Encryption of items no longer requires app pool permissions on the machine's certificate store.

## What this means for Privilege Manager

New installations of Privilege Manager will no longer require that the application pool user has to have permission to access the certificate stores. Previously this permission was required in order to encrypt and decrypt items in the database.

Existing installs of Privilege Manager (10.4 and earlier) should not remove this permission and should not remove old certificates as they will still need them to decrypt old items which predate this change. Both the web setup page and the installers will create a local __encryption.config__ file in the TMS directory to hold the keys to the key stored in the database. This file is highly sensitive and should be regarded with caution.
