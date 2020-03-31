[title]: # (MacOS Specifics)
[tags]: # (ui)
[priority]: # (1)
# MacOS Specifics & Best Practices

This best practices section pertains to all macOS versions from __El Capitan__ to (and including) __Catalina__.

Thycotic supports elevation without having to enter admin credentials for these preference panes:

* Date & Time
* Energy Saver
* Network

Other preference panes should not be used in elevation policies based on the nature of their function within the system. They can be elevated, but for certain actions, admin credentials may still be required. Changing those preference panes' settings should really be done by administrators only and not standard users, as designed by Apple&reg;.

All macOS preference panes can be used in deny policies.

This section contains macOS specific user interface topics.

* [Best Practices System Preferences](bp-sys-pref.md)
* [Best Practices Printer Installs](bp-printer.md)
* [Date & Time Preference Pane](bp-date-time.md)
* [Energy Saver Preference Pane](bp-energy-saver.md)
* [Network Preference Pane](bp-network.md)
* [Preference Pane macOS](prefpane.md)
