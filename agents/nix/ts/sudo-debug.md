[title]: # (Enable Sudo Debug)
[tags]: # (agents,unix/linux)
[priority]: # (2)
[display]: # (none)

# How to Enable sudo Debug

1. Edit __/etc/sudo.conf__.

   `vi /etc/sudo.conf`
1. Insert the following above the _Plugin sudoers_policy /opt/thycotic/lib64/pmsudo_plugin.so_ line

   `Debug pmsudo_plugin.so /var/log/sudo_debug all@notice`

1. Save and exit __sudo.conf__.

Any `sudo` command will now send debug logs to `/var/log/sudo_debug`. 

## Example Sudo debug:

```bash
Feb  3 14:10:12 sudo[13737] Checking Policy for root running [/usr/bin/env]
Feb  3 14:10:12 sudo[13737] Policy: {
	"itemId":	"8a754b45-1ab1-4ced-9f23-abe47c98e9d5",
	"priority":	65,
	"policy":	{
		"ApplicationControlPolicyContract":	{
			"ItemId":	"8a754b45-1ab1-4ced-9f23-abe47c98e9d5",
			"Name":	"New Allow",
			"ApplicationActionIds":	{
				"guid":	["61e30596-ec2e-43a2-9b4a-77bafb513afe", "f77c74c1-c77f-49d8-86bd-7910a1bb7d4f"]
			},
			"AppliesToAllProcesses":	"false",
			"ChildApplicationActionIds":	null,
			"EndsProcessing":	"false",
			"EndsProcessingChild":	"false",
			"ManditoryFilterIds":	null,
			"NegativeFileFilterIds":	null,
			"PositiveFileFilterIds":	{
				"guid":	["22d340f1-6c47-426f-ae7d-e02ce50ed364"]
			},
			"Priority":	"65",
			"SendActionEvent":	"true",
			"SkipDuringSystemStartup":	"false",
			"Stage2Processing":	"false"
		}
	}
}
Feb  3 14:10:12 sudo[13737] AdvancedCommandlineContract filter NOT matched regex pattern [/usr/bin/id] to [/usr/bin/env]
Feb  3 14:10:12 sudo[13737] AdvancedCommandlineContract filter matched glob pattern [/usr/bin/env] to [/usr/bin/env]
Feb  3 14:10:12 sudo[13737] Policy [New Allow] matched, auditing event
Feb  3 14:10:12 sudo[13737] AdvancedCommandlineContract filter NOT matched regex pattern [/usr/bin/id] to [/usr/bin/env]
Feb  3 14:10:12 sudo[13737] AdvancedCommandlineContract filter matched glob pattern [/usr/bin/env] to [/usr/bin/env], new command [/usr/bin/env]
Feb  3 14:10:12 sudo[13737] Action DisplayUserMessageContract message [hello root]
Feb  3 14:10:12 sudo[13737] Action AdjustEnvironmentalVariableContract set [PATH=/root/perl5/bin:/usr/lib64/qt-3.3/bin:/home/ctaylor/perl5/bin:/usr/local/bin:/usr/bin:/usr/sbin:/home/ctaylor/.local/bin:/home/ctaylor/bin:/home/ctaylor/bin/netbeans-11.2/netbeans/bin:/usr/sbin:/usr/sbin:/home/ctaylor/.local/bin:/home/ctaylor/bin:/home/ctaylor/bin/netbeans-11.2/netbeans/bin:/usr/sbin:/usr/sbin:/tmp/foo]
Feb  3 14:10:12 sudo[13737] Action AdjustEnvironmentalVariableContract set [BAR=foo]
```
