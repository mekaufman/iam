---

copyright:

  years: 2018, 2019

lastupdated: "2019-05-16"

keywords: remove user, delete user, user management

subcollection: iam

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:tip: .tip}

# Removing users
{: #remove}

When you remove a user from the account, the user can no longer log in to the console, switch to the account, or access account resources.
{:shortdesc}

Only account owners or users with the following access can remove users from an account:

* An IAM policy for the User management account management service with the Administrator role assigned and be the Cloud Foundry org manager if the user belongs to a Cloud Foundry org.
* If you have classic infrastructure in your account, then a user must be an ancestor of the user in the classic infrastructure user hierarchy with the Manage user classic infrastructure permission assigned. You must also have an IAM policy for the User management account management service with the Administrator role assigned or be the Cloud Foundry org manager if the user belongs to a Cloud Foundry org.

To remove a user from an account, complete the following steps:

1. From the menu bar, click **Manage** &gt; **Access (IAM)**, and select **Users**.
2. From the row of the user that you want to remove, select **Remove user** from the **Actions** ![List of actions icon](../icons/action-menu-icon.svg) menu.

If you get an error message that a classic infrastructure user can't be removed, make sure that any descendants in the user hierarchy for that user are [assigned a new parent](/docs/iam?topic=iam-update-parent), [disabled in the account](/docs/iam?topic=iam-status), or deleted, then try again.
{: tip}
