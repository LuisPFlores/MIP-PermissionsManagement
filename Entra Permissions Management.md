---
title:  Entra Permissions Management Delivery guide
description: How to execute Identity Assessment with Entra Permissions Management in your organization.
services: CIEM
author: luflores
reviewer: stevenvd
date: 06/02/2022

---
# Entra Permissions Management Delivery Guide

## Overview
Microsoft Entra Permissions Management is a cloud infrastructure entitlement management (CIEM) solution that provides comprehensive visibility into permissions assigned to all identities – users and workloads – actions, and resources across cloud infrastructures and identity providers. It detects, right-sizes, and monitors unused and excessive permissions and enables Zero Trust security through least privilege access in Microsoft Azure, AWS, and GCP.

## Scoping

## Permissions Management Console
**To display the User management dashboard**:

- In the upper right of the Permissions Management home page, select **User** (your initials) in the upper right of the screen, and then select **User management.**

    The **User Management** dashboard has two tabs:

    - **Users**: Displays information about registered users.
    - **Groups**: Displays information about groups.

### Manage users

Use the **Users** tab to display the following information about users:

- **Name** and **Email Address**: The user's name and email address.
- **Joined On**: The date the user registered on the system.
- **Recent Activity**: The date the user last used their permissions to access the system.
- The ellipses **(...)**  menu: Select the ellipses, and then select **View Permissions** to open the **View User Permission** box.

    - To view details about the user's permissions, select one of the following options:
        - **Admin for all Authorization System Types** provides **View**, **Control**, and **Approve** permissions for all authorization system types.
        - **Admin for selected Authorization System Types** provides **View**, **Control**, and **Approve** permissions for selected authorization system types.
        - **Custom** provides **View**, **Control**, and **Approve** permissions for the authorization system types you select.

You can also select the following options:

- **Reload**: Select this option to refresh the information displayed in the **User** table.
- **Search**: Enter a name or email address to search for a specific user.

### Manage groups

Use the **Groups** tab to display the following information about groups:

- **Name**: Displays the registered user's name and email address.
- **Permissions**:
    - The **Authorization Systems** and the type of permissions the user has been granted: **Admin for all Authorization System Types**, **Admin for selected Authorization System Types**, or **Custom**.
    - Information about the **Viewer**, **Controller**, **Approver**, and **Requestor**.
- **Modified By**: The email address of the user who modified the group.
- **Modified On**: The date the user last modified the group.

- The ellipses **(...)** menu: Select the ellipses to:

    - **View Permissions**:  Select this option to view details about the group's permissions, and then select one of the following options:
        - **Admin for all Authorization System Types** provides **View**, **Control**, and **Approve** permissions for all authorization system types.
        - **Admin for selected Authorization System Types** provides **View**, **Control**, and **Approve** permissions for selected authorization system types.
        - **Custom** provides **View**, **Control**, and **Approve** permissions for specific authorization system types that you select.

    - **Edit Permissions**: Select this option to modify the group's permissions.
    - **Delete**: Select this option to delete the group's permissions.

        The **Delete Permission** box asks you to confirm that you want to delete the group.
        - Select **Delete** if you want to delete the group, **Cancel** to discard your changes.
## Remediations Steps:Automation

The **Remediation** dashboard in Permissions Management provides an overview of roles/policies, permissions, a list of existing requests for permissions, and requests for permissions you have made.

> [!NOTE]
> To view the **Remediation** dashboard, your must have **Viewer**, **Controller**, or **Administrator** permissions. To make changes on this dashboard, you must have **Controller** or **Administrator** permissions. If you don't have these permissions, contact your system administrator.

> [!NOTE]
> Microsoft Azure uses the term *role* for what other cloud providers call *policy*. Permissions Management automatically makes this terminology change when you select the authorization system type. In the user documentation, we use *role/policy* to refer to both.

## Display the Remediation dashboard

1. On the Permissions Management home page, select the **Remediation** tab.

    The **Remediation** dashboard includes six subtabs:

    - **Roles/Policies**: Use this subtab to perform Create Read Update Delete (CRUD) operations on roles/policies.
    - **Permissions**: Use this subtab to perform Read Update Delete (RUD) on granted permissions.
    - **Role/Policy Template**: Use this subtab to create a template for roles/policies template.
    - **Requests**: Use this subtab to view approved, pending, and processed Permission on Demand (POD) requests.
    - **My Requests**: Use this tab to manage lifecycle of the POD request either created by you or needs your approval.
    - **Settings**: Use this subtab to select **Request Role/Policy Filters**, **Request Settings**, and **Auto-Approve** settings.

1. Use the dropdown to select the **Authorization System Type** and **Authorization System**, and then select **Apply**.

## View and create roles/policies

The **Role/Policies** subtab provides the following settings that you can use to view and create a role/policy.

- **Authorization System Type**: Displays a dropdown with authorization system types you can access, Amazon Web Services (AWS), Microsoft Azure, and Google Cloud Platform (GCP).
- **Authorization System**: Displays a list of authorization systems accounts you can access.
- **Policy Type**: A dropdown with available role/policy types. You can select **All**, **Custom**, **System**, or **Permissions Management Only**.
- **Policy Status**: A dropdown with available role/policy statuses. You can select **All**, **Assigned**, or **Unassigned**.
- **Policy Usage**: A dropdown with **All** or **Unused** roles/policies.
- **Apply**: Select this option to save the changes you've made.
- **Reset Filter**: Select this option to discard the changes you've made.

The **Policy list** displays a list of existing roles/policies and the following information about each role/policy.

- **Policy Name**: The name of the roles/policies available to you.
- **Policy Type**: **Custom**, **System**, or **Permissions Management Only**
- **Actions**
    - Select **Clone** to create a duplicate copy of the role/policy.
    - Select **Modify** to change the existing role/policy.
    - Select **Delete** to delete the role/policy.

Other options available to you:
- **Search**: Select this option to search for a specific role/policy.
- **Reload**: Select this option to refresh the displayed list of roles/policies.
- **Export CSV**: Select this option to export the displayed list of roles/policies as a comma-separated values (CSV) file.

    When the file is successfully exported, a message appears: **Exported Successfully.**

    - Check your email for a message from the Permissions Management Customer Success Team. This email contains a link to:
        - The **Role Policy Details** report in CSV format.
        - The **Reports** dashboard where you can configure how and when you can automatically receive reports.
- **Create Role/Policy**: Select this option to create a new role/policy. For more information, see [Create a role/policy](how-to-create-role-policy.md).
- 

## Operationalize Permissions Management


## Closeout