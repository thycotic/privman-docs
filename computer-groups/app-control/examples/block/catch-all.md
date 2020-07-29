[title]: # (Catch-all Deny)
[tags]: # (deny)
[priority]: # (5)
# Catch-all Deny

A catch-all deny policy is the last policy executed following the execution of a group of allow list policies. This enables you to configure your allow list to allow approved applications, like the Windows directory or other installed applications, and then to deny everything else, like applications downloaded from the internet or a thumb drive.

To create a catch-all deny policy, follow these steps:

1. Under your Computer Group select Application Policies and click __Create Policy__.
1. Select __Skip the wizard, take me to a blank policy__ to create a blank policy.
1. Enter a name and description, change the default priority value to a higher number, for example 99 and click __Create__.
1. Under __Conditions__, click __Add Exclusions__.
1. Search for and __Add__ the __LocalSystem and Service applications__ filter.
1. Click __Update__.
1. On the bottom of the policy page, click __Show Advanced__.
1. Under __Policy Enforcement__, ensure only __Stage 2 processing__ is set to active.

   ![catch-all](images/catch-all.png "Policy Enforcement under show advanced")
1. Click __Save Changes__.
1. Set the __Inactive__ switch to __Active__.

If you are creating a new catch-all policy to be used in conjunction with allow list policies, please verify that the allow list is catching all system applications and that the new deny policy is the last policy executed. For additional safety you can define the exclude any parameter to exclude system and service applications.
