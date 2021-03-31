[title]: # (Allow Listing)
[tags]: # (elevate)
[priority]: # (2)
# Allow Listing Policies

Allow listing is a type of policy that allows applications to run on your endpoints. You can think of allow listing as a neutral policy type because it does not alter an application’s default permissions, it merely signifies that the application is “known/trusted” and allowed to run. Although simple allow listing follows normal, user-level credentials, allow listed applications are also often paired with Elevation Policies outlined [Elevation Policies](../elevate/index.md).

The following examples are available:

* [Allow MS Security Catalog](ms-sec-cat.md)
* [Allow Google Application with File Upload](google-app-file-up.md)

## Allow Listing Policies without Actions

If an application is allowlisted under a user context instead of group context and without an action specified, Thycotic recommends to use the [Administrators (Include Disabled)](../../../../admin/filters/default-filters.md#user_context_filters) filter for the policy to execute as desired.
