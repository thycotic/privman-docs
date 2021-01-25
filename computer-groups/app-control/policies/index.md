[title]: # (Policies)
[tags]: # (application control, endpoints)
[priority]: # (10)
# Policies

In Application Control, layered Policies create the backbone or parameters, that dictate precisely how privileges are accessed across your network. They define what a user can run, and where. A policy is made up of customizable filters that apply an action to specific Computer Groups. In other words, each policy is defined by:

* Filters - What criteria needs to be met to apply this policy?
* Targets - Where should this policy be applied?
* Actions - What should happen to the applications this policy applies to? (i.e. blocked, allowed, etc.)

During the creation of a Policy you will specify Actions and Targets, and Filters that are created separately but then assigned to Policies.

The __Privilege Manager Policy Wizard__, guides users through the policy creation process, with step-by-step decision making guidance.

## Using Policy Templates

Privilege Manager ships with most commonly used policy templates. These are utilized by the policy wizard when creating a new policy.

Thycotic also provides templates that do not ship with the product, but that can be downloaded via __Config Feeds__ from within the Privilege Manager Console. Once downloaded and installed, customers can access those policy templates via __Admin | Folders__. Here a new policy can be created based on a template from a drop-down list. This policy will have associated targets, filters, and actions set, which can be further customized to cover an organization's specific needs. Also refer to [Configuration Feeds](../../../admin/config-feeds/index.md).

## Overview of the Configuration Process

While there are many different types of policies, the setup process must follow these basic steps:

1. Collect File Data - This enables Privilege Manager to recognize specific files and file types in your environment. The file data that you want to target with policies are called Events. All imported files can be viewed under __File Inventory__.
1. Create Filters - This step sorts important file data (Events) according to different criteria.
1. Create Policies - This step defines what
   1. Actions to perform on applications and the
   1. Targets (Locations) for those actions.
1. Assign Filters to Policies - This step directs a Policy's actions to the appropriate Events happening on your network.
1. Order your Policies based on priority level - Once your policies are created, the order they execute across your network matters. See the Policy Priority section in this guide for more details.

## Collecting File Data

Before Privilege Manager can do anything else for Application Control, it must be able to recognize files or file types in your environment like applications or executables that run. File data can be collected in several ways:

* Event Discovery - Discover active applications on your network by setting up Learning Mode Policies
* File Upload - Directly upload a specific file that you want to target
* Remote File Inventory Task (Windows/macOS) - Scans endpoints directly and imports all file data (both active and inactive files) that exist on the targeted machine(s).

## Points to Consider

If you configure Privilege Manager policies incorrectly they could prevent services or programs from starting or running with the proper rights.

Policies are evaluated in order based on the Policy Priority value on the Policy. If a blocking policy that denies applications is too broad and is set with too high a priority, it can unintentionally prevent other applications from running or letting the user request approval to run.

You can avoid conflicts resulting from incorrectly configured Privilege Manager policies by using the following best practices:

* Always test policies on machines which mirror the production environment before rolling out to production.
* Assign policies that allow processes a lower policy priority number than policies that deny processes.
* Make sure your other policy enforcement settings check boxes are selected or cleared, depending on the aims of your policy.
* Policies that deny processes always exclude the following application filters:
  * LocalSystem and Service
  * Signed Security Catalog
* You should (almost) never use wildcards in deny policies. Wildcards should be considered only after performing extensive testing.
* Do not add User Context filters as the only application target to a policy. Starting with Privilege Manager version 11, the UI does alert to this as being an invalid policy. Refer to [Warning Banner indicating Filter Error Conditions in Policies](error-conditions.md).
