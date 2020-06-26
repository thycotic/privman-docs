[title]: # (Best Practice)
[tags]: # (policy, deny, allow, best practice)
[priority]: # (2)
# Best Practice Using a Secondary File Filter

<!-- TODO: UPDATE BASED ON WIZARD APPROACH AND ONLY USE ONE EXAMPLE (.BAT) FOR BLANK POLICY. Work will be done via https://thycotic.visualstudio.com/Thycotic.ManagementServer/_workitems/edit/184325 -->

## Best Practices - File Inventory

As a best practice you create an elevate policy with a priority of X (for example 20) to elevate or allow specific scripts or files to run. Then you add a policy with a priority of X+1 (for this example 21) to deny any other execution of the command processor, PowerShell, or Microsoft installer files. For this example .msi is used.

### Creating the Allow notepad++\*.msi Filter

1. In the Privilege Manager Console under __Computer Groups__ navigate to __Application Policies__.
2. On the Filter page, click **Add New Filter**.
3. On the New Filter page, select the platform. This can be either **Both Windows / Mac OS**, **Windows**, or **Mac OS**. For this example, select **Windows**.
4. From the Filter Type drop-down select **File Specification Filter**.

   ![File Specification Filter](images/sff/file_spec_filter.png)

5. Enter the name and a description for the filter, for example “notepad++\*.msi”
6. Click **Create**.
7. The page for the new filter opens, click **Edit**.
8. Under File Specifications in the File Name field enter either a single file name, file specification, or RegEx. 

   ![Filter Name](images/sff/file_specifications.png)

   For this example, we use RegEx **(notepad\\+\\+[ a*z0*9\\.]+)** to elevate any Notepad++ version.

9. Verify that First Discovered is set to **Anytime**.
10. Click **Save**.

### Creating the Secondary Filter

1. In the Privilege Manager Console navigate to **Admin | More | Filters**.
2. On the Filter page, click **Add New Filter**.
3. On the New Filter page, select the platform. This can be either **Both Windows / Mac OS**, **Windows**, or **Mac OS**. For this example, select **Windows**.

4. From the Filter Type drop*down select **Secondary File Filter**. 

   ![Secondary File Filter](images/sff/secondary_file_filter.png)

5. Enter the name and a description for the filter, for example “secondary file filter for notepad++ msi files”.
6. Click **Create**.
7. The page for the new filter opens, click **Edit**.
8. Under Settings click **+Add** to add the **notepad++\*.msi** application filter created in “Creating the Allow notepad++\*.msi Filter” procedure. 

   ![Adding File Filter](images/sff/sff_notepad_msi2.png)

9. Click **Save**.

### Creating the Allow a Specific .msi File to Run Policy

1. Navigate to **Admin | Policies**.
2. Click **Add New Policy**.
3. From the Platform drop*down select **Windows**.
4. From the Policy Type drop*down select **Show All Templates**.
5. From the Template Type drop*down select **Other: Empty Policy**.
6. Enter a Name and Description, click **Create**.
7. Click **Edit**.
8. On the **General** tab in the Status area set the policy to **Enabled**.
9. Select the **Conditions** tab.
10. Under Application Targets click **+ Add Application Target**.
11. In Search, enter command and select **Microsoft Installer File Filter** from the list, click **Add**.
12. Under Inclusion Filters click **+ Add Inclusion Filter**.
13. In Search, enter secondary and select the **allow notepad++\*any version secondary file filter** created in “Creating the Secondary Filter” procedure steps, click **Add**.

    ![Inclusion Filter](images/sff/policy_notepad_msi.png)

    Targets are automatically added based on the policy template selected.

14. Click **Save**.

### Creating the .msi Deny Policy

1. Navigate to **Admin | Policies**.
2. Click **Add New Policy**.
3. From the Platform drop*down select **Windows**.
4. From the Policy Type drop*down select **Blacklist / Deny Application Execution**.
5. From the Template Type drop*down select the **Blacklist: Deny Specific Applications**.
6. Enter a Name, for example “deny .msi execution” and Description. 

   ![Blacklist Policy](images/sff/deny_msi_all.png)

7. Click **Create**.
8. Click **Edit**.
9. On the **General** tab in the Status area set the policy to **Enabled**.
10. Set the **Policy Priority** to **21**.
11. Select the **Blacklist** tab.
12. Select **Modal Deny Message** and keep the selection for **Send Event Feedback to Server**.
13. Click **Add Existing File Filter**.
14. Search for Microsoft and select **Microsoft Installer File Filter**, click **Add**. 

    ![MSI filter](images/sff/bl_msi_filter_def.png)

    Once added this filter is listed as msiexec.exe in the list. 
    Targets are automatically added based on the policy template selected.

15. Click **Save**.

## Updating the Endpoints with the Policies

After adding new filters and policies, the endpoints need to be updated to
enforce the new rules.

This can be done directly:

1. On the Policy Details page select the **Deployment** tab.
2. Click **Run Policy Targeting Update**.

From any other location in the Privilege Manager console follow these steps:

1. Navigate to **Admin | Config**.
2. Select the **General** tab.
3. Click **Policy Targeting Update**.



