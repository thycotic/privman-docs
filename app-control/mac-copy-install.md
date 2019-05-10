[title]: # (Mac OS Copy Install Application)
[tags]: # (standard user, policy)
[priority]: # (4100)
# Allow Copy/Install of Applications

A policy can be created to allow or deny standard users to install specific applications by copying/pulling the application into the Applications folder. Follow this example to create a policy that will enable this functionality for your Mac OS user.

1. Navigate to __Admin | Policies__ and click the __Add New Policy__ button.
1. From the Platform drop-down select __Mac OS__.
1. From the Policy Type drop-down select __Show All Templates__.
1. From the Template Type drop-down select __Other: Empty Policy__.
1. Enter a name and description for the new policy and click __Create__.
1. Once the policy is created, specify the Conditions and Filters:
   1. Click __+ Add Application Target__ to specify an application bundles filter for Mac OS applications.
   1. Click __+ Add Inclusion Filter__ to specify the Copy Install Application filter.
   1. Click __Save__.

   ![Example allow copy/drag application to applications folder](images/mac/allow_copy_conditions_20190510.png)
1. Navigate to the __General__ tab.
1. Click __Edit__.
1. Select the __Enabled__ checkbox to enable the policy.
   ![Enable the Copy Install Application policy](images/mac/allow_copy_enable_20190510.png)
1. Click __Save__.