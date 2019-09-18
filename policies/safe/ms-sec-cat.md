[title]: # (MS Security Catalog)
[tags]: # (whitelist)
[priority]: # (3)
# MS Security Catalog

This policy uses a built-in filter to whitelist Microsoft’s Signed Security Catalog. This filter is often used to dynamically whitelist update items from Microsoft.  Whitelisting these executables clears them so they are not effected by any other policy, (i.e. they are allowed to run).

1. Navigate to __Admin | Policies__, then click on Create a New Policy.
1. From the Platform drop-down select __Windows__.
1. Select __Show All Templates as a Policy Type__ click __Other: Empty Policy as a Template Type__.
1. Name the policy and add a Description.
1. Click __Create__.
1. Under the Conditions tab choose __Edit__, then __Add Inclusion Filter__.
1. Type __Present in Signed Security Catalog__ in the search bar to pull up the correct filter for this use case.
1. Click __Add__.
1. Click __Save__.
1. Navigate to the __General__ tab and click __Edit__.
1. Check the __Enabled__ box to activate this policy.
1. Click __Save__.

There is no need to add actions under the Actions tab, because these applications are Whitelisted, they are allowed to run with default permissions.
