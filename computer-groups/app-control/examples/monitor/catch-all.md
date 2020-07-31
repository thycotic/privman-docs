[title]: # (Catch-All Policy)
[tags]: # (greylist)
[priority]: # (5)
# Catch-All Policy

A useful Learning Mode Policy to set up in Production environments is called a Catch-All Policy. This type of policy will gather information on any executables in your environment that are not satisfied by other Privilege Manager policies.

>**Note**: These types of Catch-all monitor policies SHOULD NOT BE used for the Windows or Mac OS Computer Groups. Those groups apply to ALL computers in the environment and unless a monitor policy like this is setup to work with really good allow policies in front a lot of events will be sent.

1. Under your Computer Group for which you want to monitor all activities select __Application Policies__ and click __Create Policy__.
1. From the Policy Wizard select __Monitoring__ and click __Next Step__.
1. Select __Everything__ and click __Next Step__.
1. Enter a name, for example _Catch-all Monitor Policy_.
1. Click __Create Policy__.

   ![policy](images/catch-all-1.png "Catch-All Policy")
1. Customize the policies Conditions, Actions, and Policy Enforcement, for example:
   * Under Applications Targeted, click __Add Application Target__ and search for and add __Interactive Users__.
   * Under Exclusions, click __Edit__ and add __LocalSystem and Service applications__ to the exclusion list.

     ![customized](images/catch-all-2.png "Customized catch-all monitoring policy")
   * Under __Show Advanced | Policy Enforcement__ set the switch for __Stage 2 Processing__ to active an all others to inactive.

     ![enforcement](images/catch-all-3.png "Policy Enforcement settings")
1. Click __Save Changes__
1. Set the __Inactive__ switch to __Active__.
