[title]: # (Mobile Console Requirements)
[tags]: # (mobile)
[priority]: # (15001)
# Mobile Console Requirements

This document lists the requirements for installing the Privilege Manager Mobile Console.

1. Privilege Manager must be installed on a Windows Server that is attached to a domain (on-prem or cloud).
1. For on-premises instances, the Microsoft Service Bus Relay must be configured. For instructions, go to [Azure Service Bus Configuration](../how-to/infrastructure/ms-az-service-bus.md).
1. For cloud instances, Privilege Manager and Azure Active Directory must be setup and the mobile application registration must be added to the same domain. Refer to https://azure.microsoft.com/en-us/documentation/articles/active-directory-aadconnect/ For instructions, go to [Configure the Microsoft Azure Active Directory](cfg-azure-ad.md).
