[title]: # (Advanced Messages not working for child processes of Microsoft Edge)
[tags]: # (agents)
[priority]: # (2)
# Advanced Messages not working for child processes of Microsoft Edge

On Windows 10 version 1803 when choosing to Run an application in Microsoft Edge advanced messages do not work.

## Detailed Information

If an application control policy targets an application such as the Google Chrome installer, the approval or justification messages will prevent the process from continuing until the message prompt is completed. However, when choosing the "Run" option when downloading an application in Microsoft Edge, the process will be created under the browser_broker.exe service and in Windows 10 version 1803 the process continues and does not wait for the Privilege Manager message to be completed.

Other versions of Windows 10 and Microsoft Edge do not appear to have this issue.

## Workaround

An application control policy can be created to block browser_broker.exe and prevent users from using the "Run" option in Microsoft Edge.

Alternatively, upgrading Windows 10 will also fix the issue.
