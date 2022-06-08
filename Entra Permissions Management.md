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

## Operationalize Permissions Management


## Closeout