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
 
- **Identify cloud enviroments to run risk assessment** (Production Azure Subscriptions, AWS Accounts, GCP Projects)

- **Setup and onboarding**  Enable Entra Permissions Management in customer´s Azure AD Tenant and onboard cloud environments (Azure,AWS,GCP)
- **Data collection (~24 hours)** Gather all data from cloud environments

## Permissions Management Console
**To display the User management dashboard**:

- In the upper right of the Permissions Management home page, select **User** (your initials) in the upper right of the screen, and then select **User management.**

    The **User Management** dashboard has two tabs:

    - **Users**: Displays information about registered users.
    - **Groups**: Displays information about groups.

#### Manage users

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

#### Manage groups

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

#### Display the Remediation dashboard

1. On the Permissions Management home page, select the **Remediation** tab.

    The **Remediation** dashboard includes six subtabs:

    - **Roles/Policies**: Use this subtab to perform Create Read Update Delete (CRUD) operations on roles/policies.
    - **Permissions**: Use this subtab to perform Read Update Delete (RUD) on granted permissions.
    - **Role/Policy Template**: Use this subtab to create a template for roles/policies template.
    - **Requests**: Use this subtab to view approved, pending, and processed Permission on Demand (POD) requests.
    - **My Requests**: Use this tab to manage lifecycle of the POD request either created by you or needs your approval.
    - **Settings**: Use this subtab to select **Request Role/Policy Filters**, **Request Settings**, and **Auto-Approve** settings.

1. Use the dropdown to select the **Authorization System Type** and **Authorization System**, and then select **Apply**.

#### View and create roles/policies

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
- **Create Role/Policy**: Select this option to create a new role/policy. For more information, see [Create a role/policy](https://docs.microsoft.com/en-us/azure/active-directory/cloud-infrastructure-entitlement-management/how-to-create-role-policy).

You can create and approve requests for the Amazon Web Services (AWS), Microsoft Azure, or Google Cloud Platform (GCP) authorization systems.

The **Remediation** dashboard has two privilege-on-demand (POD) workflows you can use:
- **New Request**: The workflow used by a user to create a request for permissions for a specified duration.
- **Approver**: The workflow used by an approver to review and approve or reject a user's request for permissions.

#### Create a request for permissions

1. On the Permissions Management home page, select the **Remediation** tab, and then select the **My Requests** subtab.

    The **My Requests** subtab displays the following options:
    - **Pending**: A list of requests you've made but haven't yet been reviewed.
    - **Approved**: A list of requests that have been reviewed and approved by the approver. These requests have either already been activated or are in the process of being activated.
    - **Processed**: A summary of the requests you've created that have been approved (**Done**), **Rejected**, and requests that have been **Canceled**.

1. To create a request for permissions, select **New Request**.
1. In the **Roles/Tasks** page:
    1. From the **Authorization System Type** dropdown, select the authorization system type you want to access: **AWS**, **Azure** or **GCP**.
    1. From the **Authorization System** dropdown, select the accounts you want to access.
    1. From the **Identity** dropdown, select the identity on whose behalf you're requesting access.

        - If the identity you select is a Security Assertions Markup Language (SAML) user, and since a SAML user accesses the system through assumption of a role, select the user's role in **Role**.

        - If the identity you select is a local user, to select the policies you want:
            1. Select **Request Policy(s)**.
            1. In **Available Policies**, select the policies you want.
            1. To select a specific policy, select the plus sign, and then find and select the policy you want.

            The policies you've selected appear in the **Selected policies** box.

        - If the identity you select is a local user, to select the tasks you want:
            1. Select **Request Task(s)**.
            1. In **Available Tasks**, select the tasks you want.
            1. To select a specific task, select the plus sign, and then select the task you want.

            The tasks you've selected appear in the **Selected Tasks** box.

    If the user already has existing policies, they're displayed in **Existing Policies**.
1. Select **Next**.

1. If you selected **AWS**, the **Scope** page appears.

    1. In **Select Scope**, select:
        - **All Resources**
        - **Specific Resources**, and then select the resources you want.
        - **No Resources**
    1. In **Request Conditions**:
        1. Select **JSON** to add a JSON block of code.
        1. Select **Done** to accept the code you've entered, or **Clear** to delete what you've entered and start again.
    1. In **Effect**, select **Allow** or **Deny.**
    1. Select **Next**.

1. The **Confirmation** page appears.
1. In **Request Summary**, enter a summary for your request.
1. Optional: In **Note**, enter a note for the approver.
1. In **Schedule**, select when (how quickly) you want your request to be processed:
    - **ASAP**
    - **Once**
        - In **Create Schedule**, select the **Frequency**, **Date**, **Time**, and **For** the required duration, then select **Schedule**.
    - **Daily**
    - **Weekly**
    - **Monthly**
1. Select **Submit**.

    The following message appears: **Your Request Has Been Successfully Submitted.**

    The request you submitted is now listed in **Pending Requests**.

#### Approve or reject a request for permissions

1. On the Permissions Management home page, select the **Remediation** tab, and then select the **My requests** subtab.
1. To view a list of requests that haven't yet been reviewed, select **Pending Requests**.
1. In the **Request Summary** list, select the ellipses **(…)** menu on the right of a request, and then select:

    - **Details** to view the details of the request.
    - **Approve** to approve the request.
    - **Reject** to reject the request.

1. (Optional) add a note to the requestor, and then select **Confirm.**

    The **Approved** subtab displays a list of requests that have been reviewed and approved by the approver. These requests have either already been activated or are in the process of being activated.
    The **Processed** subtab displays a summary of the requests that have been approved or rejected, and requests that have been canceled.

## Operationalize Permissions Management

Permissions Management has various types of system report types available that capture specific sets of data.These reports allow management to:
- Make timely decisions.
- Analyze trends and system/user performance.
- Identify trends in data and high risk areas so that management can address issues more quickly and improve their efficiency.

#### Explore the Reports dashboard

The **Reports** dashboard provides a table of information with both system reports and custom reports. The **Reports** dashboard defaults to the **System Reports** tab, which has the following details:

- **Report Name**: The name of the report.
- **Category**: The type of report. For example, **Permission**.
- **Authorization Systems**: Displays which authorizations the custom report applies to.
- **Format**: Displays the output format the report can be generated in. For example, comma-separated values (CSV) format, portable document format (PDF), or Microsoft Excel Open XML Spreadsheet (XLSX) format.

 - To download a report, select the down arrow to the right of the report name, or from the ellipses **(...)** menu, select **Download**.

  The following message displays across the top of the screen in green if the download is successful: **Successfully Started To Generate On Demand Report**.

#### Available system reports

Permissions Management offers the following reports for management associated with the authorization systems noted in parenthesis:

- **Access Key Entitlements And Usage**:
    - **Summary of report**: Provides information about access key, for example, permissions, usage, and rotation date.
    - **Applies to**: Amazon Web Services (AWS) and Microsoft Azure
    - **Report output type**: CSV
    - **Ability to collate report**: Yes
    - **Type of report**: **Summary** or **Detailed**
    - **Use cases**:
        - The access key age, last rotation date, and last usage date is available in the summary report to help with key rotation.
        - The granted task and Permissions creep index (PCI) score to take action on the keys.

- **User Entitlements And Usage**:
    - **Summary of report**: Provides information about the identities' permissions, for example, entitlement, usage, and PCI.
    - **Applies to**: AWS, Azure, and Google Cloud Platform (GCP)
    - **Report output type**: CSV
    - **Ability to collate report**: Yes
    - **Type of report**: **Summary** or **Detailed**
    - **Use cases**:
         - The data displayed on the **Usage Analytics** screen is downloaded as part of the **Summary** report. The user's detailed permissions usage is listed in the **Detailed** report.

- **Group Entitlements And Usage**:
    - **Summary of report**: Provides information about the group's permissions, for example, entitlement, usage, and PCI.
    - **Applies to**: AWS, Azure, and GCP
    - **Report output type**: CSV
    - **Ability to collate report**: Yes
    - **Type of report**: **Summary**
    - **Use cases**:
         - All group level entitlements and permission assignments, PCIs, and the number of members are listed as part of this report.

- **Identity Permissions**:
    - **Summary of report**: Report on identities that have specific permissions, for example, identities that have permission to delete any S3 buckets.
    - **Applies to**: AWS, Azure, and GCP
    - **Report output type**: CSV
    - **Ability to collate report**: No
    - **Type of report**: **Summary**
    - **Use cases**:
         - Any task usage or specific task usage via User/Group/Role/App can be tracked with this report.

- **Identity privilege activity report**
    - **Summary of report**: Provides information about permission changes that have occurred in the selected duration.
    - **Applies to**: AWS, Azure, and GCP
    - **Report output type**: PDF
    - **Ability to collate report**: No
    - **Type of report**: **Summary**
    - **Use cases**:
        - Any identity permission change can be captured using this report.
        - The **Identity Privilege Activity** report has the following main sections: **User Summary**, **Group Summary**, **Role Summary**, and **Delete Task Summary**.
        - The **User** summary lists the current granted permissions and high-risk permissions and resources accessed in 1 day, 7 days, or 30 days. There are subsections for newly added or deleted users, users with PCI change, and High-risk active/inactive users.
        - The **Group** summary lists the administrator level groups with the current granted permissions and high-risk permissions and resources accessed in 1 day, 7 days, or 30 days. There are subsections for newly added or deleted groups, groups with PCI change, and High-risk active/inactive groups.
        - The **Role summary** lists similar details as **Group Summary**.
        - The **Delete Task summary** section lists the number of times the **Delete task** has been executed in the given time period.

- **Permissions Analytics Report**
    - **Summary of report**: Provides information about the violation of key security best practices.
    - **Applies to**: AWS, Azure, and GCP
    - **Report output type**: CSV
    - **Ability to collate report**: Yes
    - **Type of report**: **Detailed**
    - **Use cases**:
         - This report lists the different key findings in the selected auth systems. The key findings include super identities, inactive identities, over provisioned active identities, storage bucket hygiene, and access key age (for AWS only). The report helps administrators to visualize the findings across the organization.

    For more information about this report, see [Permissions analytics report](product-permissions-analytics-reports.md).

- **Role/Policy Details**
    - **Summary of report**: Provides information about roles and policies.
    - **Applies to**: AWS, Azure, GCP
    - **Report output type**: CSV
    - **Ability to collate report**: No
    - **Type of report**: **Summary**
    - **Use cases**:
         - Assigned/Unassigned, custom/system policy, and the used/unused condition is captured in this report for any specific, or all, AWS accounts. Similar data can be captured for Azure/GCP for the assigned/unassigned roles.

- **PCI History**
    - **Summary of report**: Provides a report of privilege creep index (PCI) history.
    - **Applies to**: AWS, Azure, GCP
    - **Report output type**: CSV
    - **Ability to collate report**: Yes
    - **Type of report**: **Summary**
    - **Use cases**:
         - This report plots the trend of the PCI by displaying the monthly PCI history for each authorization system.

- **All Permissions for Identity**
    - **Summary of report**: Provides results of all permissions for identities.
    - **Applies to**: AWS, Azure, GCP
    - **Report output type**: CSV
    - **Ability to collate report**: Yes
    - **Type of report**: **Detailed**
    - **Use cases**:
         - This report lists all the assigned permissions for the selected identities.


#### Generate a system report

1. In the Permissions Management home page, select the **Reports** tab, and then select the **Systems Reports** subtab.
    The **Systems Reports** subtab displays the following options in the **Reports** table:

    - **Report Name**: The name of the report.
    - **Category**: The type of report: **Permission**.
    - **Authorization System**: The authorization system activity in the report: Amazon Web Services (AWS), Microsoft Azure (Azure), and Google Cloud Platform (GCP).
    - **Format**: The format in which the report is available: comma-separated values (**CSV**) format, portable document format (**PDF**), or Microsoft Excel Open XML Spreadsheet (**XLSX**) format.

1. In the **Report Name** column, find the report you want, and then select the down arrow to the right of the report name to download the report.

    Or, from the ellipses **(...)** menu, select **Download**.

    The following message displays: **Successfully Started To Generate On Demand Report.**

    > [!NOTE]
    > If you select one authorization system, the report includes a summary. If you select more than one authorization system, the report does not include a summary.

1. To refresh the list of reports, select **Reload**.

#### Search for a system report

1. On the **Systems Reports** subtab, select **Search**.
1. In the **Search** box, enter the name of the report you want.

    The **Systems Reports** subtab displays a list of reports that match your search criteria.
1. Select a report from the **Report Name** column.
1. To download a report, select the down arrow to the right of the report name, or from the ellipses **(...)** menu, select **Download**.
1. To refresh the list of reports, select **Reload**.


#### Create a custom report

1. In the Permissions Management home page, select the **Reports** tab, and then select the **Custom Reports** subtab.
1. Select **New Custom Report**.
1. In the **Report Name** box, enter a name for your report.
1. From the **Report Based on** list:
    1. To view which authorization systems the report applies to, hover over each report name.
    1. To view a description of a report, select the report.
1. Select a report you want to use as the base for your custom report, and then select **Next**.
1. In the **MyReport** box, select the **Authorization System** you want: Amazon Web Services (**AWS**), Microsoft Azure (**Azure**), or Google Cloud Platform (**GCP**).

1. To add specific accounts, select the **List** subtab, and then select **All** or the account names.
1. To add specific folders, select the **Folders** subtab, and then select **All** or the folder names.

1. Select the **Report Format** subtab, and then select the format for your report: comma-separated values (**CSV**) file, portable document format (**PDF**), or Microsoft Excel Open XML Spreadsheet (**XLSX**) file.
1. Select the **Schedule** tab, and then select the frequency for your report, from **None** up to **Monthly**.

    - For **Hourly** and **Daily** options, set the start date by choosing from the **Calendar** dropdown, and can input a specific time of the day they want to receive the report.

    In addition to date and time, the **Weekly** and **Biweekly** provide options for you to select on which day(s)of the week the report should repeat.

1. Select **Save**.

      The following message displays across the top of the screen in green if the download is successful: **Report has been created**.
The report name appears in the **Reports** table.

#### View a custom report

1. In the Permissions Management home page, select the **Reports** tab, and then select the **Custom Reports** subtab.

    The **Custom Reports** tab displays the following information in the **Reports** table:

    - **Report Name**: The name of the report.
    - **Category**: The type of report: **Permission**.
    - **Authorization System**: The authorization system in which you can view the report: AWS, Azure, and GCP.
    - **Format**: The format of the report, **CSV**, **PDF**, or **XLSX** format.

1. To view a report, from the **Report Name** column, select the report you want.
1. To download a report, select the down arrow to the right of the report name, or from the ellipses **(...)** menu, select **Download**.
1. To refresh the list of reports, select **Reload**.

#### Share a custom report

1. In the Permissions Management home page, select the **Reports** tab, and then select the **Custom Reports** subtab.
1. In the **Reports** table, select a report and then select the ellipses (**...**) icon.
1. In the **Report Settings** box, select **Share with**.
1. In the **Search Email to add** box, enter the name of other Permissions Management user(s).

    You can only share reports with other Permissions Management users.
1. Select **Save**.

#### Search for a custom report

1. In the Permissions Management home page, select the **Reports** tab, and then select the **Custom Reports** subtab.
1. On the **Custom Reports** tab, select **Search**.
1. In the **Search** box, enter the name of the report you want.

    The **Custom Reports** tab displays a list of reports that match your search criteria.
1. Select the report you want.
1. To download a report, select the down arrow to the right of the report name, or from the ellipses **(...)** menu, select **Download**.
1. To refresh the list of reports, select **Reload**.


#### Modify a saved or scheduled custom report

1. In the Permissions Management home page, select the **Reports** tab, and then select the **Custom Reports** subtab.
1. Hover over the report name on the **Custom Reports** tab.

    - To rename the report, select **Edit** (the pencil icon), and enter a new name.
    - To change the settings for your report, select **Settings** (the gear icon). Make your changes, and then select **Save**.

    - To download a copy of the report, select the **Down arrow** icon.

1. To perform other actions to the report, select the ellipses (**...**) icon:

    - **Download**: Downloads a copy of the report.

    - **Report Settings**: Displays the settings for the report, including scheduling, sharing the report, and so on.

    - **Duplicate**: Creates a duplicate of the report called **"Copy of XXX"**. Any reports not created by the current user are listed as **Duplicate**.

         When you select **Duplicate**, a box appears asking if you're sure you want to create a duplicate. Select **Confirm**.

         When the report is successfully duplicated, the following message displays: **Report generated successfully**.

    - **API Settings**: Download the report using your Application Programming Interface (API) settings.

         When this option is selected, the **API Settings** window opens and displays the **Report ID** and **Secret Key**. Select **Generate New Key**.

    - **Delete**: Select this option to delete the report.

         After selecting **Delete**, a pop-up box appears asking if the user is sure they want to delete the report. Select **Confirm**.

        **Report is deleted successfully** appears across the top of the screen in green if successfully deleted.

    - **Unsubscribe**: Unsubscribe the user from receiving scheduled reports and notifications.

         This option is only available after a report has been scheduled.

## Automate Anomaly Detections
#### Display the Activity triggers dashboard

- In the Permissions Management home page, select **Activity triggers** (the bell icon).

    The **Activity triggers** dashboard has four tabs:

    - **Activity**
    - **Rule-Based Anomaly**
    - **Statistical Anomaly**
    - **Permission Analytics**

    Each tab has two subtabs:

    - **Alerts**
    - **Alert Triggers**

#### View information about alerts

The **Alerts** subtab in the **Activity**, **Rule-Based Anomaly**, **Statistical Anomaly**, and **Permission Analytics** tabs display the following information:

- **Alert Name**: Select **All** alert names or specific ones.
- **Date**: Select **Last 24 hours**, **Last 2 Days**, **Last Week**, or **Custom Range.**

    - If you select **Custom Range**, also enter **From** and **To** duration settings.
- **Apply**: Select this option to activate your settings.
- **Reset Filter**: Select this option to discard your settings.
- **Reload**: Select this option to refresh the displayed information.
- **Create Activity Trigger**: Select this option to [create a new alert trigger](how-to-create-alert-trigger.md).
- The **Alerts** table displays a list of alerts with the following information:
    - **Alerts**: The name of the alert.
    - **# of users subscribed**: The number of users who have subscribed to the alert.
    - **Created By**: The name of the user who created the alert.
    - **Modified By**: The name of the user who modified the alert.

The **Rule-Based Anomaly** tab and the **Statistical Anomaly** tab both have one more option:

- **Columns**: Select the columns you want to display: **Task**, **Resource**, and **Identity**.
    - To return to the system default settings, select **Reset to default**.

#### View information about alert triggers

The **Alert Triggers** subtab in the **Activity**, **Rule-Based Anomaly**, **Statistical Anomaly**, and **Permission Analytics** tab displays the following information:

- **Status**: Select the alert status you want to display: **All**, **Activated**, or **Deactivated**.
- **Apply**: Select this option to activate your settings.
- **Reset Filter**: Select this option to discard your settings.
- **Reload**: Select **Reload** to refresh the displayed information.
- **Create Activity Trigger**: Select this option to [create a new alert trigger](how-to-create-alert-trigger.md).
- The **Triggers** table displays a list of triggers with the following information:
    - **Alerts**: The name of the alert.
    - **# of users subscribed**: The number of users who have subscribed to the alert.
    - **Created By**: The name of the user who created the alert.
    - **Modified By**: The name of the user who modified the alert.

## Closeout