---

copyright:

  years: 2017, 2019

lastupdated: "2019-01-28"

keywords: get started with IAM, IAM tutorial, IAM quick start

subcollection: iam

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:tip: .tip}
{:note: .note}

# Getting started tutorial
{: #getstarted}

This tutorial is intended to help you get up and running quickly with IBM Cloud Identity and Access Management (IAM) by inviting users to your account and assigning Cloud IAM access to those users.
{:shortdesc}

This tutorial is for IAM-enabled resources. For services that don't support creating Cloud IAM policies for managing access, you can use [Cloud Foundry access](/docs/iam?topic=iam-cfaccess#cfaccess) or [classic infrastructure permissions](/docs/iam?topic=iam-infrapermission#infrapermission).
{: note}


## Step 1. Invite users and assign initial access
{: #step1}

You can invite one or multiple users and set an initial access policy for the users on the invitation. If you invite multiple users in one invitation, the same access is assigned to each of the users. In the access section of the Invite users page, you see only the sections that you have access to assign.

As the account owner, you can assign Cloud IAM roles for users that you invite in the Services section. You can provide access to all resources in a resource group, all resources for a specific service in a resource group, all Identity and Access enabled services in the account, a single resource in the account, or access to account management services:

1. Go to **Manage** &gt; **Access (IAM)**, and select **Users**.
2. Click **Invite users**.
3. Specify the email address of the users that you want to invite.
4. In the **Access** section, expand the **Services** option.
5. Choose to assign access to a **Resource**, resources within a **Resource group**, or **Account management services**.
6. Depending on your selection, follow the prompts to specify the wanted access. If you selected the resource group option, you can also provide the user with access to view, edit, or manage access to the resource group by selecting a role for access to the resource group.
7. If you have permission, you can also assign Cloud Foundry or infrastructure access on the invitation.
8. Click **Invite users**.

For more information, see [Inviting users and assigning access](/docs/iam?topic=iam-iamuserinv#iamuserinv).

## Step 2. Create access groups
{: #step2}

To streamline the process of assigning access to users in your account, you can create access groups. Access groups are a way to organize users and service IDs that you can then easily assign access to by defining a single policy for the entire group.

### Set up your groups
{: #group_setup}

To create an access group, complete the following steps:

1. From the menu bar, click **Manage** &gt; **Access (IAM)**, and select **Access Groups**.
2. Click **Create**.
3. Enter a name and optional description for your group
4. Click **Create**.

Next, continue to set up your group by adding users or service IDs:

1. Select the name of the group that you want to add to.
2. Click **Add users**.
3. Select the users that you want to add from the list, and click **Add to group**.
4. To add service IDs to the group, click **Service IDs**.
5. Select the IDs that you want to add from the list, and click **Add to group**.

### Assign access to your groups
{: #group_access}

After you create your groups, you can assign access to all entities within the group with a single policy or multiple policies.

1. From the menu bar, click **Manage** &gt; **Access (IAM)**, and select **Access Groups**.
2. Select the name of the group that you want to assign access for.
3. From the **Access policies** tab, click **Assign access** to set up an access policy. Repeat as needed to assign more access.

By organizing resources in resource groups and users in access groups, you can assign a group of users access to a group of resources with a single policy, which reduces the overall number of policies you need to manage.
{: tip}


## Step 3. Manage access for existing users
{: #user_access_manage}

After you invite users, assign initial access, and create your access groups, you might want to assign more access or edit the initial access that you assigned to ensure all users and groups in your account have the wanted level of access.

### Assigning new access
{: #new_access}

To assign a new access policy, complete the following steps:

1. From the menu bar, click **Manage** &gt; **Access (IAM)**, and select **Users**.
2. Select the name of the user that you want to assign access.
3. Click **Access policies**.
4. Click **Assign access**.
5. Choose how you want to assign access:
    * Select **Assign access within a resource group** to assign access to all resources within a group or to just resources for a specific service within a group. You can also provide the user with access to view, edit, or manage access to the resource group by selecting a role for access to the resource group. Select **No access** if you want the user to have only access to the specified resource and not the group that it's organized in.
    * Select **Assign access to resources** to assign access to all Identity and Access enabled resources across the account, all resources of a specific service across the account, a single instance, or a single resource within a specific service instance.
    * Select **Assign access to Account management services** to assign access to all account management services or just one account management service.
5. Select any combination of roles to define the scope of access. For more information, see [Cloud IAM roles](/docs/iam?topic=iam-iamusermanrol#iamusermanrol).
6. Click **Assign**.


### Editing existing access
{: #editing_access}

You can update existing access by editing the assigned roles for a user.

1. From the menu bar, click **Manage** &gt; **Access (IAM)**, and select **Users**.
2. Select the name of the user that you want to edit access for.
3. Click **Access policies**.
4. Click **Edit** from the **Actions** ![List of actions icon](../icons/action-menu-icon.svg) menu on the row for the policy that you want to edit.
4. Edit the policy by updating the assigned roles.
5. Click **Save**.

You can remove access from a user by clicking the **Remove** option from the **Actions** ![List of actions icon](../icons/action-menu-icon.svg) menu for the policy that you want to remove.

## Next steps
{: #next}

Learn what else you can do with Cloud IAM by checking out the [Cloud IAM features](/docs/iam?topic=iam-features#features) list.
