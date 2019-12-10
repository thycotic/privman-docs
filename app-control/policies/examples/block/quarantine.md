[title]: # (Quarantine Malware)
[tags]: # (deny)
[priority]: # (4301)
# Quarantine Specified Malware

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
