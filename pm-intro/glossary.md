[title]: # (Glossary)
[tags]: # ( )
[priority]: # (99)
# Glossary

__Action__ -  An action is not required in a policy. A policy can be designed, for example, to simply listen for specific application activity, and provide auditing information back to Privilege Manager. However, to apply controls to a process (executable), one defines an action in the policy.

Some common actions include:

* Adjust process rights, 
* Add administrative rights,
* Remove administrative rights,
* Deny application execution,
* Require user justification – user provides a reason why they need to run the application,
* Application warning,
* Bypass UAC prompt,
* Require workflow approval – user needs approval to run an application, etc.

__Agent__ - An agent is installed on every endpoint in your network and will 1) Receive and apply defined policies to govern application/process execution on the endpoint, 2) Execute tasks on the endpoint and feed audit and inventory data back to Privilege Manager.

__Agent BaseUrl__ - The agent must be set to communicate directly with Privilege Manager. There exists a registry entry that is set upon agent installation – this registry key is called BaseUrl.  

__Agent Registration__ – The Privilege Manager agent completes a registration process when it initially contacts Privilege Manager following installation, but also at regular configurable intervals. So, registration occurs regularly.

__Arellia__ – Arellia was the original name for Privilege Manager. Because of this, many file paths and back end notations include the term Arellia or AMS instead of Privilege Manager or TMS.

__Computer Groups__ – (also called Resource Targets) Specified sets of computers that meet certain criteria (e.g. type of operating system, location of the computer, etc) that are targeted by certain policies and scheduled tasks.

__Condition__ – Policy Conditions contain one or more filters that defines what a policy is ‘listening’ for.  If the condition is satisfied in a policy, then an action is applied.

__Config Feeds__ – Config Feeds can be found on the ADMIN page access from the Privilege Manager main page. Configuration feeds allow Thycotic to deliver new components to Privilege Manager.  Simply click through the options in the Config Feeds page starting with the Select Items button and download anything appropriate.  Once the item is downloaded, it is immediately available in Privilege Manager.

__Dashboard__ – Dashboard is the term for Privilege Manager’s landing page, or Home screen.

__Event__ – Any notable file data on your network that is targeted by Privilege Manager is called an Event.

__Discovery__ – Discovery is a term used by Thycotic for any information that is scanned or “found” on a network and imported or used by our products.

__Least Privilege__ – Least Privilege is a security strategy organized around best practices. When effectively implemented, an organization’s employees can navigate their network system with the lowest level of privileges. Higher credentials are flexibly (and often automatically) granted or denied based on users and the tasks being performed. This dynamic strategy significantly reduces the threat of security breaches across an organization without interfering with daily operations.

__Filter__ – The Policy Condition lists one or more filters.  A filter is defined to identify many things about an executable or process, or ‘situation’ when an executable or process is initiated. 

Common Filters include:

* File specifications,
* Network location,
* Directory location,
* Application reputation,
* Application digital certificate,
* Time of day, User context (what AD security group a user belongs),
* Download source,
* Drive type,
* File owner,
* Internet Zone,
* Security Catalogs, etc.

__Inclusion Filter/Exclusion Filter__ – When a filter is placed in the Inclusion Filters or Exclusion Filters under the Conditions tab of a policy definition, it can be used to explicitly include or exclude what is defined in the filter with respect to a policy.  (I.e. Exclusion: apply this policy only if the user is NOT an administrator; Inclusion: apply this policy only if the computer is on the company network; Inclusion: apply this policy only to applications signed by a specific company’s digital certificate, etc.). 

__Persona__ - Personas manage sets of privileges that are assigned to users on specific Windows computers or Computer Groups. A Persona includes a set of pre-defined filters and provide an easy way to assign policies based on Computer Groups and users. Filter parameters in a Persona are limited and specifically designed to be applied to Windows administrative users.

__Policy__ – A set of conditions (Filters) that, when met, will apply an action to managed resources (target computers).

* __Blocking__ – Type of policies that will deny an application from running based on a determined set of criteria.
* __Catch-All__ Policy – A Catch-All policy is a type of Learning Mode policy that will gather information about any unknown events that happen in your network.
* __Elevation Policy__ – An Elevation Policy will allow specified applications to run with administrator credentials.
* __Monitoring__ – Monitoring is a dynamic method of managing applications that might not be included on a safelist or blocklist. Instead of trying to anticipate every executable users will run, you can apply a flexible policy that includes actions or reputation checking for unknown applications.
* __Non-Blocking__ – Types of policies that will allow applications to run according to normal user credentials. This is often considered a neutral policy to specify trusted applications.

__Policy Priority__ – Policies are evaluated in a certain order for each application that runs. If one policy blocks an application and ends execution before a second policy that was intended to elevate privileges, then only the block will occur. It is important to have an awareness of all policies that are defined and the order in which they are called by the agent. 

__RDP Monitor__ – Discontinued with version 10.6. The RDP Monitor is used to configure the Enhanced Session Monitoring feature in Secret Server.  It is found in Privilege Manage because this feature uses the agent architecture defined by Privilege Manager, however this feature typically is not used in a Privilege Manager PoC.

__Reputation Engine__ – Privilege Manager can call upon a reputation engine (e.g. VirusTotal) in real-time to check an application’s public reputation.  One can create a reputation checking policy in Privilege Manager through Monitoring policies.  This type of policy can take application information and send it to the engine in real-time and act on the application based on the returned reputation. For example, if the reputation engine returns a BAD grade, the application can be denied. It is recommended to apply this type of policy to specific directories where new or unknown applications might reside – like the Downloads, TEMP, or Desktop directory. 

__Resource Targets__ – (also called Computer Groups) Specified sets of computers that meet certain criteria (e.g. type of operating system, location of the computer, etc) that are targeted by certain policies and scheduled tasks. 

__Scheduled Tasks__ — A Privilege Manager policy may be defined to be applied based on a schedule. These items run using the Task Scheduler on each endpoint, and are only accessible by Privilege Manager administrators. 

__Secret Server__ – Secret Server is a second Thycotic product that many IT teams use to securely manage privileged accounts and passwords in an organization. Privilege Manager and Secret Server are separate products but often used together for a holistic approach to network security. The two products are highly integrated and some of the features cross between products. For example, the Secret Server license page houses Privilege Manager licenses, and Secret Server clients rely on Privilege Manager agent (RDP Monitor) when using the advanced session recording feature.

__Send Policy Feedback__ – Send Policy Feedback is a setting that can be enabled for any policy that sends information to Privilege Manager. This is used in Learning Mode Policies and often valuable during testing, configuration, or auditing projects.

__TMS__ – TMS is shorthand for Thycotic Management Server. It is an umbrella term for our base application layer that Privilege Manager runs on top of.

__VirusTotal__ – The VirusTotal reputation service is supported by Privilege Manager as a reputation engine.  A free VirusTotal API key will need to be obtained to use VirusTotal in Privilege Manager. Note that the free API has limits and may not be appropriate for a production environment that functions with over four requests per minute.
