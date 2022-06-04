# Cloud Identity Assessment Delivery Guide

#### Overview

#### Scoping

#### Setup

##### Prerequisites
To enable Permissions Management in your organization:

You must have an Azure AD tenant. If you don't already have one, create a free account.
You must be eligible for or have an active assignment to the global administrator role as a user in that tenant.

In your browser:

Go to Azure services and use your credentials to sign in to Azure Active Directory.

If you aren't already authenticated, sign in as a global administrator user.
If needed, activate the global administrator role in your Azure AD tenant.
In the Azure AD portal, select Features highlights, and then select Permissions Management.
If you're prompted to select a sign in account, sign in as a global administrator for a specified tenant.

The Welcome to Permissions Management screen appears, displaying information on how to enable Permissions Management on your tenant.

To provide access to the Permissions Management application, create a service principal.

An Azure service principal is a security identity used by user-created apps, services, and automation tools to access specific Azure resources.

[!NOTE] To complete this step, you must have Azure CLI or Azure PowerShell on your system, or an Azure subscription where you can run Cloud Shell.

To create a service principal that points to the Permissions Management application via Cloud Shell:

Copy the script on the Welcome screen:

az ad sp create --id b46c3ac5-9da6-418f-a849-0a07a10b3c6c

If you have an Azure subscription, return to the Azure AD portal and select Cloud Shell on the navigation bar. If you don't have an Azure subscription, open a command prompt on a Windows Server.

If you have an Azure subscription, paste the script into Cloud Shell and press Enter.

For information on how to create a service principal through the Azure portal, see Create an Azure service principal with the Azure CLI.

For information on the az command and how to sign in with the no subscriptions flag, see az login.

For information on how to create a service principal via Azure PowerShell, see Create an Azure service principal with Azure PowerShell.

After the script runs successfully, the service principal attributes for Permissions Management display. Confirm the attributes.

The Cloud Infrastructure Entitlement Management application displays in the Azure AD portal under Enterprise applications.

Return to the Welcome to Permissions Management screen and select Enable Permissions Management.

You have now completed enabling Permissions Management on your tenant. Permissions Management launches with the Data Collectors dashboard.

## View a training video on enabling Permissions Management

- To view a video on how to enable Permissions Management in your Azure AD tenant, select [Enable Permissions Management in your Azure AD tenant](https://www.youtube.com/watch?v=-fkfeZyevoo).

#### Assessment

#### Reporting

some links to add

#### Closeout