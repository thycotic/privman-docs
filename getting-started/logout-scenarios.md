[title]: # (Login and Logout Scenarios)
[tags]: # (on-prem)
[priority]: # (503)

# Login and Logout Scenarios

Based on authentication provider configured and used, the login and logout prompts and scenarios differ.

## Login Options

Sample images with various login options set up.

![alt](images/scenarios/sample-login-options.png "Sample login options")

### Basic login (Standard Out-Of-Box)

![alt](images/scenarios/standard-NTML-login.png "Standard local login")

### Basic login (Secret Server)

![alt](images/scenarios/basic-secserv.png "Default Secret Server login")

### Azure AD

![alt](images/scenarios/azure-ad.png "Default Azure AD login")

## Logout Scenarios

### Basic with NTLM 

After the logout completes and the tokens are cleared, the user is presented with a prompt to close the browser.

![alt](images/scenarios/standard-logout.png "Standard local login")

### Azure AD

After the logout completes and the user tokens are cleared, the user is redirected to the Thycotic One login modal.

![alt](images/scenarios/login-t1.png "Redirect to Thycotic One login after logout")
