# Installation hangs with error: Worker Role Monitor received exception during ping

During the installation of Privilege Manager the install hangs and is unable to procced to the next step of the installation.

After checking the Thycotic Monitor, you see the below error in the log viewer:

*Worker Role Monitor received exception during ping: The HTTP request is
unauthorized with client authentication scheme 'Negotiate'. The authentication
header received from the server was 'Negotiate,NTLM'*

![](images/worker-role-monitor-received-exception-during-ping/7bd0223405f1fc912d58c7c9720e9a2a.png)

**Note:** This error is due to a host name in the binding within IIS.

Resolve
-------

1.  Open **Internet Information Services (IIS) Manager**.

    ![](images/worker-role-monitor-received-exception-during-ping/75bd9f380a86e3b7fb5e8ff62429e5ff.png)

2.  Expand down to **Sites**.

    ![](images/worker-role-monitor-received-exception-during-ping/a277ba811722e5323b1ee26c7be1a15e.png)

3.  Click **Default Web Site** or the **top node site**.

    ![](images/worker-role-monitor-received-exception-during-ping/a64f91c8516e6277891239c8912e2b37.png)

4.  Click **Bindings**.

    ![](images/worker-role-monitor-received-exception-during-ping/84f883781d3d10beb1043286d69e6f1d.png)

5.  Select the **HTTPS binding** \| click **Edit.**

    ![](images/worker-role-monitor-received-exception-during-ping/352e083d056df6a77b24eb660601e70d.png)

6.  Confirm that there is no Hostname included for the HTTPS binding for the TMS
    site. If so, please delete it.

    ![](images/worker-role-monitor-received-exception-during-ping/2555f55e5fc57b11305a674001869660.png)

7.  **Recycle** all the TMS application pools in IIS.

    ![](images/worker-role-monitor-received-exception-during-ping/74bac5f111d87bf547b8cdeac6ce863f.png)

8.  Try the install again by going to **https://localhost/TMS/Setup**.
