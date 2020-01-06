[title]: # (Setting up ActiveX Policies)
[tags]: # (elevate)
[priority]: # (2)
# Setting up ActiveX Policies

Setting up ActiveX Policies – this is to allow add-ins to be installed over at a browser (in this example Internet Explorer). To test if ActiveX can be installed without prompting UAC, we can do a test run at <http://pcpitstop.com/>; ActiveX installation is in turn provided at <https://pcpitstop.com/testax.asp>.

>**Note:** You will need to import local group policy definitions before editing your Active-X Group Policy Settings.

## Overview

1. Create a policy for the list of websites.
1. Create a task to send the policies to the endpoints (this is for Resource Targeting).
1. Test the policy.

## Creating the Policy

1. Navigate to **Admin** | **Policies** | **ActiveX** tab.

   ![ActiveX](images/active/14bbbe50f97f865b2b310b17aaa66fda.png)
1. Click on **Add New Policy**.

   ![Add New Policy](images/active/f599edfecb0a25b9ca5a6a9f765830f1.png)
1. After the Policy has been created, navigate to the **Other Sites** Tab and add
the URL (protocols included).

   ![Other Sites](images/active/ddef8b4737b7f7823bfeed647a55dfdc.png)

Other options to consider:

* Ignore Invalid Certificate Date

* Ignore Invalid Certificate Name (CN)

* Ignore Unknown Certification Authority (CA)

* Ignore Wrong Certificate Usage

## Task and Resource Targeting

1. Navigate to __ADMIN | More… | Folders__.

   ![Folders](images/active/e83cf30c2f254d53948b5dab8118ae3c.png)
1. Open the folder tree and navigate to **Policies | General | Windows**.

   ![Windows](images/active/db6ec5e530a59d66db519bfc5b604466.png)
1. Click **Add New**.

1. From the Template drop-down select **General Scheduled Client Task**.

1. Enter a Name and Description.

1. For Client Command select **Apply Group Policy Settings**.

1. Verify/add the Resource Target selection.

1. Click **Create**.

   ![Create](images/active/97dc7018559ca8e52e980cc181a13eed.png)

   >**Note:** Apply Group Policy Settings when you have 2 or more ActiveX
policies to add to the Parameters.

   ![Group Policy Settings ](images/active/e28e94024cf6b5d52e833ae626d9cfca.png)

1. Navigate to the **Parameters** Tab to add the ActiveX Policy that you
    previously created.

   ![Parameters](images/active/55bf3dd273c1a73d48137b6bd88eb1fd.png)

## Configure the Triggers and the Targets

Proceed to configuring both the Policy and Task functions. On completing this
configuration, Privilege Manager Triggers feature will then send the configured
task to the targeted endpoint.

To view the Task, go to the **Task Scheduler**. You must have administrator
access to view the task inside Thycotic folder.

   ![Task Scheduler](images/active/49b9ffe96a27ec13268763d889d89279.png)

## Test the Policy

Go to the website:
[https://pcpitstop.com/testax.asp](http://pcpitstop.com/testax.asp) and install
the **Add-in**.

You should see the **Time and Date** as seen in the image below.

   ![Time and Date](images/active/c1c02061c05456d4b4e14688db556012.png)
