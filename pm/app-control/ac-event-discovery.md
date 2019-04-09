[title]: # (Learning Mode Policies - Send Policy Feedback)
[tags]: # (Application Control,Event Discovery,Learning Mode,Policy Feedback)
[priority]: # (213)
# Learning Mode Policies – Send Policy Feedback

At the most basic level, a Learning Mode Policy is a policy that takes no action, it exists only to gather data and you can use the data it gathers for audits or for assigning actions to application events retrospectively. For trials and Proof of Concept (PoC) environments these can be pointed at specific endpoints in order to learn about events that are already happening, or in order to test-run specific applications that you want to quickly introduce into Privilege Manager.

Any Learning Mode Policy will have the Send Policy Feedback check-box checked under the Policy’s Actions tab.

>**Note**:
>Send Policy Feedback is generally disabled in production environments outside of specific auditing or data-collecting initiatives due to the large amount of data these policies can gather.

<User-added image>

## Discover Applications that Require Administrator Rights

The most influential applications are those that require administrator credentials to run. For setting up endpoints that are organized by Least Privilege, you can use a Learning Mode Policy to discover all events requiring Administrator rights.

1. From Application Control’s Dashboard, navigate to Event Discovery. Next, click on Configuration.
<User-added image>
1. Here, you will see a list of pre-configured policies:
<User-added image>
1. Click Edit and check the boxes of the first four Collection Settings: Administrative Rights Detection, Administrative Rights Required Detection (Application Compatibility), Administrative Rights Required Detection (Security Manifest), and Setup Detection.
1. Click the “?” icons beside these options for explanations of each setting. Each Collection Setting listed here is a Policy that flags any event on endpoints that required a User Account Control (UAC) prompt.

## Discover All Events on Test Endpoints

Another type of Learning Mode Policy will discover all events on targeted machines regardless of whether the application requires Administrator Rights. This policy is used in test environments to quickly target policies at untrusted/unwanted applications, but is not recommended for production settings.

1. From the Event Discovery | Configuration screen select Edit and check Log all Windows/MacOS activity from Application Compatibility Testing Computers.
1. Simply checking these boxes will not activate this policy. To begin collecting data you must first specify target computers. To do so, click the text Application Compatibility Testing Computers
<User-added image>
1. Under the Filter Definition tab, click Edit, then Edit Resources to Include. Here you can add specific Resource Filters, or target machines that your new policies will run on.
<User-added image>
1. When target computers are selected, click Close, then Save

## View Policy Results

To view all feedback, or event, sent from your existing policies with the “Send Policy Feedback” activity checked, navigate from Dashboard to Event Discovery | Policy Activity. Events will be listed in the main section and on the left sidebar you can scope results for certain policies, computers, time frame, etc. You can use this view to assign any events to policies by clicking Assign to Policy under the event listing.

<User-added image>

## View Files
You can also quickly glean any new files found by Privilege Manager in the Event Discovery | Files Screen. Distinct from the Policy Events’ screen view, the Files page only shows files rather than displaying all events attached to current policies.

<User-added image>

## New Loaded Resource

<User-added image>

At the beginning of your policy creation process you will see many new events labeled as “New Loaded Resource.” This is because importing files in Privilege Manager is not the same thing as discovering information about the files. Discovery of file details is done by scheduled policies by default, but If you want to discover file details immediately, do the following:

1. Navigate to __Event Discovery | Files__.
1. Click one of your New Loaded Resource files.
1. Click Discover Now. This process may take a few minutes. If the file is not discovered, check to make sure your endpoint target resource is running. 

>**Note**:
>Files may not be discovered if they have already been deleted in your system.

<User-added image>