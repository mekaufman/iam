---

copyright:

  years: 2017, 2019

lastupdated: "2019-01-28"

keywords: Cloud Foundry access, assign access, add user to organization, Cloud Foundry roles

subcollection: iam

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}

# Managing Cloud Foundry access
{: #mngcf}

To manage access to account organizations and spaces, you must be the account owner, organization manager, or space manager.
{:shortdesc}

## Updating Cloud Foundry access
{: #update_cf_access}

1. From the menu bar, click **Manage** &gt; **Access (IAM)**, and select **Users**.
2. From the row for the user that you want to assign access, select the **Actions** ![List of actions icon](../icons/action-menu-icon.svg) menu and then click **Assign access**.
3. Select **Assign by using Cloud Foundry**.
4. Expand the row for the organization the user is assigned to in order to view the user's access to spaces and their roles in those spaces.
5. From the **Actions** ![List of actions icon](../icons/action-menu-icon.svg) menu in the Cloud Foundry section, you can:

  * Remove the user from the organization
  * Edit the organization role
  * Edit the space role

## Adding a user to an organization
{: #add_to_org}

If you are the manager of an organization that the user is not yet a member of, you assign the user to that organization.

1. From the menu bar, click **Manage** &gt; **Access (IAM)**, and select **Users**.
2. From the row for the user that you want to assign access, select the **Actions** ![List of actions icon](../icons/action-menu-icon.svg) menu, and then click **Assign access**.
3. Select **Assign by using Cloud Foundry**.
4. Select **Assign organization**.
5. Assign the user access:
   * Choose an organization to add the user to
   * Assign an organization role
   * Choose a region
   * Choose a space
   * Assign a space role
7. Click **Assign**.

## Reviewing your assigned access
{: #review_my_access}

If you need to review your assigned access in an account that you have been added to, complete the following steps:

1. From the menu bar, click **Manage** &gt; **Access (IAM)**, and select **Users**.
2. Select your name.
3. Click **Cloud Foundry access**.
3. Expand the org row, and review your assigned roles.

If you need additional access, you must contact the organization manager or account owner to update your assigned Cloud Foundry role.
