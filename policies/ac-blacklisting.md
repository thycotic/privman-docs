[title]: # (Blacklisting Policies)
[tags]: # (deny)
[priority]: # (4400)
# Blacklisting Policies

Blacklisting is a policy that denies applications from running on your endpoints based on application attributes, file hash, location, or certificates. This is a powerful type of policy and it may be used to block specific, known and unwanted applications from running. A blacklist policy can target programs that prevent productivity for your end users or applications that are known malware. If malware, you can also add a quarantine action for your blacklist policy as outlined in the second example below.

## Example: iTunes with File Upload

As we've seen, there are multiple ways to introduce a new application into Privilege Manager before assigning a policy to it. For this example we will perform a File Upload for the iTunes installer to quickly Blacklist the iTunes program from running on target endpoints.
  
First create the iTunes filter by using downloaded iTunes files:

1. On the Application Control dashboard home page, select the __Upload File__ tile.
1. Browse to select file (i.e. the iTunes installer), click __Upload File__.
1. When the file successfully uploads, choose __Go to File Details__.
1. Click __Add New Filter__. Check the Filter criteria you want to block like the File Name, the Original File Name, and the Product Name.
1. Click __Create__.

Next create the iTunes Blacklist Policy:

1. Click on the __Deny (Blacklist) Applications__ tile on the Application Control dashboard.
1. Select a __Platform__, then __Blacklist: Deny Specific Applications__.
1. Add Name and Description, click __Create__.
1. In the __Advanced Policy View__ under the __Conditions__ tab, select __Edit__.
1. Add the __Inclusion Filter__.
1. Select your iTunes filter/s.
1. click __Add__, then __Save__.
1. Under the General tab, click Edit.
1. Select __Enabled__ to enable the policy.
1. Click __Save__.

Under the Actions tab, do not change the settings, but notice it is set to Deny Execute Message. This will produce a pop-up message to the user telling them this application execution is denied.

You can edit the policy further, if needed. Adjust the Policy Priority as needed. Policy Priority will be discussed in detail later in this document.

## Example: Quarantine Specified Malware

For known cases of malware or ransomware, you can use Privilege Manager to prevent specified applications from running and place them in a quarantine. For this example we’ll target the generic executable “malware.exe,” but you can do this with any file name.

First, create your malware filter:

1. Choose the Filters Tile from the Application Control home page dashboard or navigate to ADMIN | Filters.
1. Click __Add Filter__.
1. Select __Windows__ as a platform and __Blank Win32 Executable Filter__ as a Filter Type.
1. Name your filter __Malware Example__ and add a description.
1. Click __Create__.
1. Click __Edit__ and add the file name __malware.exe__.
1. Click Save.

Next, create a Blacklist Policy that will quarantine this filter’s target.

1. From the dashboard click the __Policies__ tile.
1. Click __Add New Policy__.
1. Select __Windows__ as a Platform.
1. Select __Show All Templates__.
1. Select __Blacklist: Quarantine Specific Applications__ as a Template Type.
1. Add a Name and Description, click __Create__.
1. Click __Edit__ and the __Enabled__ checkbox.
1. Choose the Advanced Policy View button if possible.
1. Under the __Conditions__ tab, click __Edit__.
1. Add __Application Target__ and search for your malware example filter and add the filter.
1. Click __Save__.

Once this policy has been applied to your endpoint/s, any executable called malware.exe will be automatically blocked and quarantined if prompted to run
