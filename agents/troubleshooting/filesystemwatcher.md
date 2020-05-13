[title]: # (macOS - FileSystemWatcher)
[tags]: # (catalina)
[priority]: # (14)
# Catalina FileSystemWatcher Issue

On macOS Catalina there is a known issue, preventing the the agent from receiving notification of events that need to be sent to the server. To workaround this, the __Retry errored TMS Events - Catalina (macOS)__ policy can be enabled to ensure all events get sent to the server.

The defaults for this new Remote Scheduled Client Command are as follows:

* On the General tab:

  ![General Tab](images/catalina/retry-events-1.png)

* On the Triggers tab:

  Customize the schedule if necessary to best suit your particular implementation.

  ![Triggers Tab](images/catalina/retry-events-2.png)

* On the Targets tab:

  The default resource targets required are specified by default as __All macOS Catalina Computers with Application Control Agent Installed (Target)__. The results of the computer group include any macOS Catalina computers that have the agent installed and are properly configured for Application Control.

  ![Targets Tab](images/catalina/retry-events-3.png)

* On the Conditions tab:

  ![Conditions Tab](images/catalina/retry-events-4.png)

* On the Advanced Tab:

  ![Advanced Tab](images/catalina/retry-events-5.png)

Once the policy is enabled on an endpoint, the agent will perform the __Retry errored TMS Client Events (MacOS)__ command and send any events that have not been sent.
