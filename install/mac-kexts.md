[title]: # (Legacy System Extensions)
[tags]: # (macOS,kexts)
[priority]: # (1720)
# Legacy System Extensions

## Effect on Privilege Manager Customers by Apple Deprecating Kernel Extensions in macOS

In 2019, Apple announced the deprecation of kernel extensions (KEXTS) in a future OS upgrade and that System Extensions should be used instead. Beginning in macOS 10.15.4, the use of kernel extensions will trigger a notification that the software using this type of extension includes a deprecated API and an alternative should be provided by the vendor.

You may see this popup:

![popup](images/kexts.jpg "System notification about extension deprecation")

## How is this Going to Affect Privilege Manager?

Thycotic's Privilege Manager plans to remove any dependency on kernel extension in version 10.8 that will be delivered this summer. In the meantime, Privilege Manager will continue to function normally and no immediate action is required.

You can read more about legacy system extensions on [Apple's website](https://support.apple.com/en-us/HT210999).
