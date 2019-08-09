---

copyright:

  years: 2018, 2019

lastupdated: "2019-08-09"

keywords: remove user, delete user

subcollection: iam

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:tip: .tip}

# Removing users from an account
{: #remove}

When you remove a user from an account, the user can no longer log in to the console, switch to your account if they still belong to another account, or access account resources. Removing a user from an account doesn't delete the IBMid for the user.
{:shortdesc}

Only account owners or users with the following access can remove users from an account:

* An IAM policy for the User management account management service with the Administrator role assigned and be the Cloud Foundry org manager if the user belongs to a Cloud Foundry org.
* If you have classic infrastructure in your account, a user must have an IAM policy for the User management account management service with the Administrator role assigned, be the Cloud Foundry org manager if the user belongs to a Cloud Foundry org, and be an ancestor of the user in the classic infrastructure user hierarchy with the Manage user classic infrastructure permission assigned.

To remove a user from an account, complete the following steps:

1. From the menu bar, click **Manage** &gt; **Access (IAM)**, and select **Users**.
2. From the row of the user that you want to remove, select **Remove user** from the **Actions** ![List of actions icon](../icons/action-menu-icon.svg) menu.

Any resources created by the user remain in the account. However, the user no longer has access to work with those resources, so the account owner or an administrator for that service or service instance can assign other users to work with the resources or delete them from the account.

If you get an error message stating that a classic infrastructure user can't be removed, make sure that any descendants in the user hierarchy for that user are [assigned a new parent](/docs/iam?topic=iam-update-parent), [disabled in the account](/docs/iam?topic=iam-status), or deleted, and then try again.
{: tip}
