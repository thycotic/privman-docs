[title]: # (Blocking Policies)
[tags]: # (deny)
[priority]: # (5)
# Blocking Policies

Blocking is a policy that denies applications from running on your endpoints based on application attributes, file hash, location, or certificates. This is a powerful type of policy and it may be used to block specific, known and unwanted applications from running. A block policy can target programs that prevent productivity for your end users or applications that are known malware. If malware, you can also add a quarantine action for your block policy as outlined in the second example below.

Thycotic Privilege Manager controls any application on a machine. When you configure Privilege Manager correctly, targeted applications can be elevated, whitelisted, or blocked. But if you create new policies without careful consideration then you can potentially block core system processes.

Before you create new polices, keep in mind the following best practices:

* Do not enable policies until after you have configured them. As a safety precaution, all newly-created application control policies are turned off until you enable them.
* Important: New policies that you create will automatically target all applications until you add application filters that will narrow the scope.
* Additionally, Thycotic highly recommends testing all policies on a limited number of machines before they are deployed to the entire environment. See Best practices for Application Control Solution policies for more information.

The following examples are available:

* [Blocking Specific Applications](spec-app.md)
* [iTunes with File Upload](iTunes-file-up.md)
* [Quarantine Specific Malware](quarantine.md)
* [Catch-all block Policy](catch-all.md)
