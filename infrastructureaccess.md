---

copyright:

  years: 2017, 2018

lastupdated: "2018-11-30"

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:important: .important}
{:new_window: target="_blank"}

# Classic infrastructure permissions
{: #infrapermission}

When you invite a user to your account, you can select from three classic infrastructure permission sets that assign bulk access: View only, Basic user, Super user.
{:shortdesc}

You can set extra permissions after the user accepts the invitation. For example, the initial permission set assigned on the invitation doesn't grant access to devices. So, you must grant device access after the user accepts the invitation. For more information, see [Managing classic infrastructure access](/docs/iam/mnginfra.html#mngclassicinfra).

When you invite someone to the account, only you, the account owner, or a user with the Manage user classic infrastructure permission, can adjust the permissions for the user. If you're assigning the permissions and you aren't the account owner, you can assign only the level of permissions or a subset of the permissions that you're already assigned. An account owner can update anyone's permissions in the account to have any level of access.


## Migrated classic infrastructure permissions
{: #predefined}

A set of classic infrastructure permissions for viewing and managing billing information and working with support cases are now migrated to access groups. The users in your account who were previously assigned these permissions are now assigned to the respective migrated permission access group. As a result, the classic infrastructure permissions can be directly managed by using IAM access policies.

These special access groups include all the appropriate IAM policies to preserve the original behavior of the classic infrastructure permissions. For example, for a user to continue to see all updates from all users on a support case, the migrated permission access groups for the ticketing classic infrastructure permissions include an extra IAM policy on the User management service with Viewer role assigned. For more information, see [Assigning user access for working with support cases](/docs/get-support/support_access.html#access).

You can continue to manage these migrated classic infrastructure permissions for users directly through IAM by adding and removing them from the migrated permission access groups. The policies that these access groups have are locked to preserve the access behavior for their members. To maintain ease of use for newer IAM users, avoid deleting these access groups.

After your classic infrastructure permissions are migrated, you must discontinue use of those permissions. See the following table for all the migrated classic infrastructure permissions that are now part of IAM access groups.
{: important}

| Migrated Permission Access Group Name | Allowed Actions |
|----------|---------|
| View account summary | View the account summary page and invoices and payments |
| Get compliance report | Request compliance reports |
| Edit company profile | Edit the company profile information |
| One-time payments | Make one-time payments on the user's account |
| Update payment details | Update the recurring monthly payment information |
| Limit EU case restriction | Enable or disable the EU Supported option that restricts support case data to the European Union  |
| Add cases and view orders | Create support cases and see all orders.  |
| Edit cases | Edit any support case |
| Search cases | Search all support cases as long as the view cases permission is also assigned |
| View cases | View all support cases |
{: caption="Table 1. Predefined access groups" caption-side="top"}

You can continue to manage users for the access groups. However, you might find it helpful to create new access groups that include a combination of access policies for the [IAM account management services](/docs/iam?topic=iam-account-services#account-services) to make it easier to assign access for account management tasks and work with support cases.
