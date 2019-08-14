[title]: # (User Interface)
[tags]: # (troubleshooting)
[priority]: # (10000)
# User Interface and Ports

When something goes wrong in Privilege Manager, the UI has a few places worth checking:

* __Admin | Diagnostics__ - this will give you information on Agents and Operating Systems, click __Console Logs__ for more details.
* __Reports | Diagnostics__ – A great place to look for some useful programmed reports on Agents, Remote Tasks, Policies Not Received by Agents, Summary of Gauge States, and Licensing.

## Connectivity

Are you having Connectivity issues? A few things to keep in mind:

* Outbound access from the agent to the server is done by default over port 443 (the standard port for HTTPS communication), but you may specify a different port if desired.
* The only port that the agent listens on is port 5593. This is not required. For example, you can block this port and agents will pull from the server on a set schedule.
