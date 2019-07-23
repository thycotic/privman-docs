[title]: # (Overview of Filters)
[tags]: # (architecture)
[priority]: # (20)
## Overview of Filters
In Privilege Manager, using a robust filtering system is the key to creating accurate and effective Policies.

A "filter" is made up of specific criteria that Privilege Manager uses to target important file data (or Events*) that occur across your environment. You can think of Filters as the core identifiers in your Privilege Manager system. They are used to identify various levels of activity across your organization's computers, including processes (applications) that are launched on computers, who is executing an application, or the state of the computer that the process is being executed on.

*An "Event" in Privilege Manager is any piece of file data or executable on a computer that is targeted by a policy.

There are different methods for Filter-creation and usage, but if you take the time to familiarize yourself with our out-of-the-box filters they can help make your policy-creation process easy. This article will provide details and descriptions for Windows Filters in Privilege Manager and how you can begin using out-of-the-box Filters, or create your own.

## Types of Filters
We recommend leveraging Privilege Manager's out-of-the-box filters to get your policies up and running fast! For a complete list of out-of-the-box filters according to category type, review our Filters' Catalog for Privilege Manager here.

You can search your full list of available filters by navigating to Admin | Filters in Privilege Manager. If you already know what you want to target, simply try typing keywords in the search bar to check whether a filter exists that fits your target goal.

## Creating New Filters using Event Discovery

One way to begin creating new Filters that identify specific files or applications on your network is to set up a Learning Mode Policy and use the events pulled in by Privilege Manager from actions performed on a test machine. See our User Guide's section on "Event Discovery" for more information on setting up a Learning Mode Policy.

In Privilege Manager, navigate to Admin | Event Discovery | Files. Under a recognized event, clicking Create Filter should bring you to an Add New Filter page* with the known identifiers needed for targeting this event auto-populated.

*If you are NOT directed to an Add New Filter screen, this means Privilege Manager doesn’t have enough information to target this event yet. In these cases you may need to create Filters manually. See section below for Adding New Filters Manually.

This Add New Filter page reveals the available list of building blocks, attributes, or criteria used for creating a Windows' filter. In other words, the following list of criteria are possible data fields that Privilege Manager can look and sift for on any given event that your policies target for Windows machines. Note that criteria can vary depending on the type of filter you are creating:

* File Name
* Path
* Internal Name
* Original File Name
* File Version
* Product Name
* Product Version
* Company Name
* File Signature ("File must be signed by")

<User-added image>

You can choose which criteria to use by selecting or deselecting any of the filter line-items listed above. If you are new to the filter creation process, we recommend experimenting with these different identifiers in your test environment to ensure that you are using a comprehensive list of identifiers in your filter--enough to target the application or file intended but not too specific that variations to your target will fall through the filter's criteria hooks.

## Creating a New Filter Manually

Navigate to Admin | Filters in Privilege Manager and click Add Filter. Under Filter Details, select a platform type and then choose a Filter Type from the dropdown (see our Filters’ Catalog for descriptions of filter types). Name your new filter and type a Description, then click Create.

Editing options for this new filter will depend on the type of filter selected.

## Create A Copy - How to Use Filter Templates

Out-of-the-Box filters are designed to be used as templates, meaning when you open these filters you will see a Create A Copy button rather than the option to immediately Edit. These filter templates are protected to provide a jumping off point whenever creating new filters. They are formed by specific criteria that you can tailor according to your specific use case after copying.

Keep in mind that every filter in Privilege Manager—whether or not it is a template—can be leveraged by the Copying feature.

<User-added image>