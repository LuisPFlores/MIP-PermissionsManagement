---
title:  Cloud Identity Assessment Delivery guide
description: How to execute Identity Assessment with Entra Permissions Management in your organization.
services: CIEM
author: luflores
reviewer: stevenvd
date: 06/02/2022

---

# Cloud Identity Assessment Delivery Guide

## Overview
Microsoft Entra Permissions Management is a cloud infrastructure entitlement management (CIEM) solution that provides comprehensive visibility into permissions assigned to all identities – users and workloads – actions, and resources across cloud infrastructures and identity providers. It detects, right-sizes, and monitors unused and excessive permissions and enables Zero Trust security through least privilege access in Microsoft Azure, AWS, and GCP.


### Purpose
The purpose of this document is to provide delivery resources a comprehensive overview of the tasks that will be required to deliver Cloud Identity Assessment. This document is intended to be shared for use by Cloud Identity Assessment resources. It is structured chronologically following the standard and typical flow of an assessment.


## Scoping
** to develop ***

## Set up and onboarding
##### Prerequisites
To enable Permissions Management in the customer´s organization:

- You must have an Azure AD tenant. If you don't already have one, [create a free account](https://azure.microsoft.com/free/).
- You must be eligible for or have an active assignment to the global administrator role as a user in that tenant.

> [!NOTE]
> During public preview, Permissions Management doesn't perform a license check.

#### How to enable Permissions Management on your Azure AD tenant

1. In your browser:
    1. Go to [Azure services](https://portal.azure.com) and use your credentials to sign in to [Azure Active Directory](https://ms.portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Overview).
    1. If you aren't already authenticated, sign in as a global administrator user.
    1. If needed, activate the global administrator role in your Azure AD tenant.
    1. In the Azure AD portal, select **Features highlights**, and then select **Permissions Management**.

    1. If you're prompted to select a sign in account, sign in as a global administrator for a specified tenant.

        The **Welcome to Permissions Management** screen appears, displaying information on how to enable Permissions Management on your tenant.

1. To provide access to the Permissions Management application, create a service principal.

    An Azure service principal is a security identity used by user-created apps, services, and automation tools to access specific Azure resources.

    > [!NOTE]
    > To complete this step, you must have Azure CLI or Azure PowerShell on your system, or an Azure subscription where you can run Cloud Shell.

    - To create a service principal that points to the Permissions Management application via Cloud Shell:

        1. Copy the script on the **Welcome** screen:

            `az ad sp create --id b46c3ac5-9da6-418f-a849-0a07a10b3c6c`

        1. If you have an Azure subscription, return to the Azure AD portal and select **Cloud Shell** on the navigation bar.
            If you don't have an Azure subscription, open a command prompt on a Windows Server.
        1. If you have an Azure subscription, paste the script into Cloud Shell and press **Enter**.

            - For information on how to create a service principal through the Azure portal, see [Create an Azure service principal with the Azure CLI](/cli/azure/create-an-azure-service-principal-azure-cli).

            - For information on the **az** command and how to sign in with the no subscriptions flag, see [az login](/cli/azure/reference-index?view=azure-cli-latest#az-login&preserve-view=true).

            - For information on how to create a service principal via Azure PowerShell, see [Create an Azure service principal with Azure PowerShell](/powershell/azure/create-azure-service-principal-azureps?view=azps-7.1.0&preserve-view=true).

        1. After the script runs successfully, the service principal attributes for Permissions Management display. Confirm the attributes.

             The **Cloud Infrastructure Entitlement Management** application displays in the Azure AD portal under **Enterprise applications**.

1. Return to the **Welcome to Permissions Management** screen and select **Enable Permissions Management**.

    You have now completed enabling Permissions Management on your tenant. Permissions Management launches with the **Data Collectors** dashboard.

#### Configure data collection settings

Use the **Data Collectors** dashboard in Permissions Management to configure data collection settings for your authorization system.

1. If the **Data Collectors** dashboard isn't displayed when Permissions Management launches:

    - In the Permissions Management home page, select **Settings** (the gear icon), and then select the **Data Collectors** subtab.

1. Select the authorization system you want: **AWS**, **Azure**, or **GCP**.

1. For information on how to onboard an AWS account, Azure subscription, or GCP project into Permissions Management, select one of the following articles and follow the instructions:

    - [Onboard an AWS account](onboard-aws.md)
    - [Onboard an Azure subscription](onboard-azure.md)
    - [Onboard a GCP project](onboard-gcp.md)

## Cloud Identity Assessment
Permissions Management provides a summary of key statistics and data about your authorization system regularly. This information is available for Amazon Web Services (AWS), Microsoft Azure, and Google Cloud Platform (GCP).

#### Components of the Permissions Management Dashboard
The Permissions Management **Dashboard** displays the following information:

- **Authorization system types**: A dropdown list of authorization system types you can access: AWS, Azure, and GCP.

- **Authorization System**: Displays a **List** of accounts and **Folders** in the selected authorization system you can access.

    - To add or remove accounts and folders, from the **Name** list, select or deselect accounts and folders, and then select **Apply**.

- The **Permission Creep Index**  heat map shows the incurred risk of users with access to high-risk permissions, and provides information about:

    - Users who were given access to high-risk permissions but aren't actively using them. *High-risk permissions* include the ability to modify or delete information in the authorization system.

    - The number of resources a user has access to, otherwise known as resource reach.

    - The high-risk permissions coupled with the number of resources a user has access to produce the score seen on the chart.

    Permissions are classified as *high*, *medium*, and *low*.

    - **High** (displayed in red) - The score is between 68 and 100. The user has access to many high-risk permissions they aren't using, and has high resource reach.
    - **Medium** (displayed in yellow) - The score is between 34 and 67. The user has access to some high-risk permissions that they use, or have medium resource reach.
    - **Low** (displayed in green) - The score is between 0 and 33. The user has access to few high-risk permissions. They use all their permissions and have low resource reach.

    The number displayed on the graph shows how many users contribute to a particular score. To view detailed data about a user, hover over the number.

    The distribution graph displays all the users who contribute to the permission creep. It displays how many users contribute to a particular score. For example, if the score from the PCI chart is 14, the graph shows how many users have a score of 14.

    - The **PCI Trend** graph shows you the historical trend of the PCI score over the last 90 days.
    - To download the **PCI history report**, select **Download**.

    #### View information on the heat map

    1. Select the number on the heat map bubble to display:
    
        - The total number of **Identities** and how many of them are in the high, medium, and low categories.
        - The **PCI trend** over the last several weeks.

- The **Identity** section below the heat map on the left side of the page shows all the relevant findings about identities, including roles that can access secret information, roles that are inactive, over provisioned active roles, and so on.

    - To expand the full list of identities, select **All findings**.

- The **Resource** section below the heat map on the right side of the page shows all the relevant findings about resources. It includes unencrypted S3 buckets, open security groups, and so on.

- **Identity**: A summary of the **Findings** that includes:
    - The number of **Inactive** identities that haven't been accessed in over 90 days.
    - The number of **Super** identities that access data regularly.
    - The number of identities that can **Access secret information**: A list of roles that can access sensitive or secret information.
    - **Over-provisioned active** identities that have more permissions than they currently access.
    - The number of identities **With permission escalation**: A list of roles that can increase permissions.

    To view the list of all identities, select **All findings**.

- **Resources**: A summary of the **Findings** that includes the number of resources that are:
    - **Open security groups**
    - **Microsoft managed keys**
    - **Instances with access to S3 buckets**
    - **Unencrypted S3 buckets**
    - **SSE-S3 Encrypted buckets**
    - **S3 Bucket accessible externally**


## Baseline Health Check for Cloud Identities


#### The Analytics summary

You can also view a summary of users and activities section on the [Analytics dashboard](https://docs.microsoft.com/en-us/azure/active-directory/cloud-infrastructure-entitlement-management/usage-analytics-home). This dashboard provides a snapshot of the following high-risk tasks or actions users have accessed, and displays the total number of users with the high-risk access, how many users are inactive or have unexecuted tasks, and how many users are active or have executed tasks:

- **Users with access to high-risk tasks**: Displays the total number of users with access to a high risk task (**Total**), how many users have access but haven't used the task (**Inactive**), and how many users are actively using the task (**Active**).

- **Users with access to delete tasks**: A subset of high-risk tasks, which displays the number of users with access to delete tasks (**Total**), how many users have the delete permissions but haven't used the permissions (**Inactive**), and how many users are actively executing the delete capability (**Active**).

- **High-risk tasks accessible by users**: Displays all available high-risk tasks in the authorization system (**Granted**), how many high-risk tasks aren't used (**Unexecuted**), and how many high-risk tasks are used (**Executed**).

- **Delete tasks accessible by users**: Displays all available delete tasks in the authorization system (**Granted**), how many delete tasks aren't used (**Unexecuted**), and how many delete tasks are used (**Executed**).

- **Resources that permit high-risk tasks**: Displays the total number of resources a user has access to (**Total**), how many resources are available but not used (**Inactive**), and how many resources are used (**Active**).

- **Resources that permit delete tasks**: Displays the total number of resources that permit delete tasks (**Total**), how many resources with delete tasks aren't used (**Inactive**), and how many resources with delete tasks are used (**Active**).


## Reporting



## Closeout