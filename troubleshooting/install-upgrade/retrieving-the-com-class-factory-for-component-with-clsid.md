# Retrieving the COM class factory error

While attempting to upgrade Privilege Manager, you receive the error message
below when accessing
[https://[YourInstanceName]/TMS/Setup](https://[YourInstanceName]/TMS/Setup).
The window is unable to load with the following error message:

*“Server Error in '/Tms/Setup' Application.*

*Retrieving the COM class factory for component with CLSID
{228FB8F7-FB53-4FD5-8C7B-FF59DE606C5B} failed due to the following error:
800703fa Illegal operation attempted on a registry key that has been marked for
deletion. (Exception from HRESULT: 0x800703FA).”*

Resolve
-------

1.  Close the browser window.

2.  Complete an IIS reset by searching for the Windows Powershell application.

3.  Right-click and select Run as Administrator.

4.  Enter in: **IISreset** \| hit **Enter**.

    ![](images/retrieving-the-com-class-factory-for-component-with-clsid/0341372347001c7ea7415c698fd128e6.png)

5.  Once the IIS reset has completed navigate back to
    [https://[YourInstanceName]/TMS/Setup](https://[YourInstanceName]/TMS/Setup).

6.  Click **Add / Update Product Features**.

    ![](images/retrieving-the-com-class-factory-for-component-with-clsid/e58128dfd07eab0b44b75ff3a5995345.png)

7.  Click **Install/Upgrade Products**.

    ![](images/retrieving-the-com-class-factory-for-component-with-clsid/540aed95f5b8269c133aa43e6e32a01c.png)

1.  Select **ALL** required solutions.

2.  Click **Install** and the upgrade process will begin.
