---

copyright:

  years: 2019

lastupdated: "2019-05-13"

keywords: migrated permissions, SoftLayer account permissions, migrated permission access group, migrated classic infrastructure permissions

subcollection: iam

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:important: .important}
{:new_window: target="_blank"}


# Managing migrated SoftLayer account permissions
{: #migrated_permissions}

Access groups now include a migrated set of SoftLayer account permissions for viewing and managing billing information and working with support cases. The users in your account who were previously assigned these permissions are now assigned to the respective migrated permission access group. As a result, the permissions can be directly managed by using IAM access groups.
{:shortdesc}

These special access groups include all the appropriate IAM policies to preserve the original behavior of the SoftLayer account permissions. For example, for a user to continue to see all updates from all users on a support case, the migrated permission access groups for the ticketing SoftLayer account permissions include an extra IAM policy on the User management service with Viewer role assigned. For more information, see [Assigning user access for working with support cases](/docs/get-support?topic=get-support-access#access).

You can continue to manage these migrated classic infrastructure permissions for users directly through IAM by adding and removing them from the migrated permission access groups. The policies that these access groups have are locked to preserve the access behavior for their members. To maintain ease of use for newer IAM users, avoid deleting these access groups.

After your classic infrastructure permissions are migrated, you must discontinue use of those permissions. See the following table for all the migrated classic infrastructure permissions that are now part of IAM access groups.
{: important}

| Migrated Permission Access Group Name | Allowed Actions |
|----------|---------|
| View account summary | View the account summary page and invoices and payments. |
| Get compliance report | Request compliance reports. |
| Edit company profile | Edit the company profile information. |
| One-time payments | Make one-time payments in the user's account. |
| Update payment details | Update the recurring monthly payment information. |
| Limit EU case restriction | Enable or disable the EU Supported option that restricts support case data to the European Union.  |
| Add cases and view orders | Create support cases and see all orders.  |
| Edit cases | Edit any support case. |
| Search cases | Search all support cases if the view cases permission is also assigned. |
| View cases | View all support cases. |
{: caption="Table 1. Predefined access groups" caption-side="top"}

