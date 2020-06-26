## MSI File Example

In this example we are creating a policy to deny running a test.msi file.

### Creating the File Filter for .msi Files

In this example we are creating a filter for the target executing .msi files.

1. In the Privilege Manager Console navigate to **Admin | More | Filters**.
2. On the Filter page, click **Add New Filter**.
3. On the New Filter page, select the platform. This can be either **Both Windows / Mac OS**, **Windows**, or **Mac OS**. For this example, select **Windows**.
4. From the Filter Type drop*down select **File Specification Filter**. This also allows you to link in hashes or signatures. 

   ![File Specification Filter](images/sff/file_spec_filter.png)

5. Enter the name and a description for the filter, for example “test.msi” and “filter for msi files”.
6. Click **Create**.
7. The page for the new filter opens, click **Edit**.
8. Under File Specifications in the File Name field enter either a single file name, file specification, or RegEx.

   ![Filter Name](images/sff/file_specifications.png)

   For this example, we use **test.msi** to police a single file name.

9. Verify that First Discovered is set to **Anytime**.
10. Click **Save**.

### Creating the Secondary Filter

In this example we are creating the secondary file filter.

1. In the Privilege Manager Console navigate to **Admin | More | Filters**.
2. On the Filter page, click **Add New Filter**.
3. On the New Filter page, select the platform. This can be either **Both Windows / Mac OS**, **Windows**, or **Mac OS**. For this example, select **Windows**.
4. From the Filter Type drop*down select **Secondary File Filter**.

   ![Secondary File Filter](images/sff/secondary_file_filter.png)

5. Enter the name and a description for the filter, for example “secondary file filter for msi files”.
6. Click **Create**.
7. The page for the new filter opens, click **Edit**.
8. Under Settings click **+Add** to add the test.msi application filter created in “Creating the File Filter for .msi Files” procedure. 

   ![Adding File Filter](images/sff/sff_msi.png)

9. Click **Save**.

### Creating the Policy

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
13. In Search, enter secondary and select **secondary filter for msi files** from the list, click **Add**. This is the filter you created in the “Creating the Secondary Filter” procedure above.

    ![Adding Inclusion Filter](images/sff/msi_conditions.png)

    Resource Targets are automatically added based on the policy template  selected.

14. Select the **Actions** tab.
15. Enable Send policy feedback.
16. Under Actions to apply to the application click **+ Add Action**.
17. Select **Application Denied Message Action** from the list, click **Add**. 

    ![Adding Exclusion Filter](images/sff/msi_actions.png)

18. Click **Save**.

