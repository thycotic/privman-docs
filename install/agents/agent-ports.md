[title]: # (Ports/Agent Access)
[tags]: # (agents)
[priority]: # (1601)
# Ports/Agent Access Information

* __Outbound (port 443 - HTTPS)__: This is the default access port through which the agent connects to the server. You may specify a different port based on your environment.
* __Inbound (port 5593)__: The is the default and only port that the agent listens on. This port is not required and you can block port 5593. If you block the port, the agents pull updates from the server based on a set schedule.
* __SQL (port 1433)__: This is the default SQL DB port. The SQL port can be customized.
