[title]: # (Boot-up Performance)
[tags]: # (policy analysis)
[priority]: # (2)
# Increase Boot-up Performance

In environments with policies having many filters, starting policy analysis during boot-up can impact the overall boot performance.

If this is an issue in your environment you can pause the policy analysis during boot. Pause analysis during the boot-phase decreases CPU utilization and delays to the boot process.

The end of the boot-phase in which policy analysis is paused, is defined as the CPU utilization after start-up being below 25% for a minimum of 120 seconds. Once that benchmark is reached, policy analysis will start.

>**Warning**:
>Using this feature opens your systems up to vulnerabilities during the boot-phase due to policies not being enforced for a certain amount of time, until the above mentioned condition is met.

## Enable Pausing Policy Analysis during Boot-up

Each policy by default has a list of policy enforcement options under __Advanced | Policy Enforcement__.

![policy enforcement](images/pause-policy-analysis.png "Policy Enforcement settings")

To enable pausing policy analysis during boot-up on filter-rich policies, set the __Pause Policy Analysis During Boot__ switch to on and save the change.
