[title]: # (macOS Specific)
[tags]: # (troubleshooting)
[priority]: # (1)
# MacOS Specific Troubleshooting

## Access to Directories

On Catalina based macOS systems, when .pkg installers are downloaded to a users home directory vs. a public folder, an error like the following example is triggered with a 256 response code:

`Error message: PrivManACS W: Unknown callback for event 3226790335 and filepath /Users/johndoe/Downloads/Microsoft_Outlook_16.32.19120802_Updater.pkg`

Catalina has a new security restriction that prevents daemons and applications that don’t have the full disk access entitlement from accessing files in certain directories in the users home directory. This includes __~/Downloads__, __~/Documents__, etc.

__~/Public__ is exempt, because it is public.

Versions prior to Catalina do not experience this restriction.
