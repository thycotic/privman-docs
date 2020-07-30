[title]: # (Catch-All Policy)
[tags]: # (greylist)
[priority]: # (4501)
# Catch-All Policy

A useful Learning Mode Policy to set up in Production environments is called a Catch-All Policy. This type of policy will gather information on any executables in your environment that are not satisfied by other Privilege Manager policies.

1. Under your Computer Groups select __Application Policies__ and click __Create Policy__.
1. From the Policy Wizard select __Monitoring__ and click __Next Step__.
1. Select __Everything__ and click __Next Step__.
1. Enter a name, for example _Catch-all Monitor Policy_.
1. Click __Create Policy__.

   ![policy](images/catch-all-1.png "Catch-All Policy")
1. Under Computer Groups Targeted, click __Add__.
1. Search for and add __Application Compatibility Testing Windows Computers (Target)__.
1. Click __Update__.
1. Click the __x__ next to __Windows Computers__ and confirm to remove this target.
1. Customize the policies Conditions, Actions, and Policy Enforcement, for example:
   * Under Applications Targeted, click __Add Application Target__ and search for and add __Interactive Users__.
   * Under Exclusions, click __Edit__ and add __LocalSystem and Service applications__ to the exclusion list.
   * Under __Show Advanced | Policy Enforcement__ set the switch for __Stage 2 Processing__ to active an all others to inactive.
1. Click __Save Changes__

   ![customized](images/catch-all-2.png "Customized catch-all monitoring policy")

   ![enforcement](images/catch-all-3.png "Policy Enforcement settings")
1. Set the __Inactive__ switch to __Active__.