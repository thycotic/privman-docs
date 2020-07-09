[title]: # (Mobile App)
[tags]: # (mobile)
[priority]: # (15000)
# Privilege Manager Mobile Application

The Privilege Manager Mobile console allows you to process approval requests, disclose passwords, and see alerts via the Privilege Manager Mobile Application on iOS and Android smartphones.

For the mobile app to work you must install the Privilege Manager Mobile Console, have Azure Active Directory setup to add an application registration, configure the Microsoft Azure Service Bus, and then install the Privilege Manager Mobile App.

The instructions are provided based on the assumptions, that

1. our customer is using Azure AD and has already configured the [Azure Active Directory App Registration](../config/foreign-systems/active-directory\set-up-privilege-manager-azure-ad-integration.md) according to the docs to allow them to authenticate as an Azure AD user. The mobile application registration must be added to that __same domain__.
1. our customer has the ability to create an Azure Service Bus service.

## Detailed Instruction Topics

To get started with the setup of the Privilege Manager Mobile Console, review and follow the instructions under the following topics in the order provided:

1. [Add the mobile application registration to your Azure Active Directory integration with Privilege Manager](cfg-azure-ad.md)
1. [Configure the Service Bus for Mobile](cfg-service-bus-mobile.md)
1. [Install and Configure the Privilege Manager Mobile Console Solution on the Privilege Manager Server](cfg-console.md)
1. [Install the Privilege Manager Mobile App on a Mobile Device](install.md)
1. [Use the Mobile Application](use-mobile.md)
