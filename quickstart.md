---

copyright:

  years: 2017, 2019

lastupdated: "2019-09-23"

keywords: get started with IAM,getting started with Identity and Access Management tutorial,IAM tutorial,IAM quick start,resource group,access group, access policy, inviting users

subcollection: iam

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:tip: .tip}
{:note: .note}

# Getting started with IAM tutorial
{: #getstarted}

Get up and running quickly with {{site.data.keyword.Bluemix_notm}} Identity and Access Management (IAM) by setting up access groups for quick access assignments, inviting users to your account, and managing their access.
{:shortdesc}

This tutorial is for IAM-enabled resources. For services that don't support creating IAM policies for managing access, you can use [Cloud Foundry access](/docs/iam?topic=iam-cfaccess#cfaccess) or [classic infrastructure permissions](/docs/iam?topic=iam-infrapermission#infrapermission).
{: note}

## Before you begin
{: #iam-before-you-begin}

If you are new to using IAM, check out the following documentation to understand more about the features, concepts, and components of the access management system:

* [IBM Cloud Identity and Access Management](/docs/iam?topic=iam-iamoverview) provides a quick overview of what IAM is in {{site.data.keyword.Bluemix_notm}}, the available features, and links to available CLI and API docs.
* [IAM concepts](/docs/iam?topic=iam-iamconcepts) outlines the high-level concepts in IAM that can help you understand the different components as you get started.
* [IAM access](/docs/iam?topic=iam-userroles) gives a more in-depth review of how access management works by using access policies.


## Step 1. Create access groups
{: #step2}

To streamline the process of assigning access to users in your account, you can create access groups. Access groups are a way to organize users and service IDs so that you can then easily assign access to by adding one or more policies for the entire group. Then, you can add or remove users and service IDs as needed instead of assigning individual access to each user.

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

After you create your access groups, you can assign access to all members of the group with one or more policies.

1. From the menu bar, click **Manage** &gt; **Access (IAM)**, and select **Access Groups**.
2. Select the name of the group that you want to assign access for.
3. From the **Access policies** tab, click **Assign access** to assign an access policy. Repeat as needed to assign more access.

By organizing resources in resource groups and users in access groups, you can assign a group of users access to a group of resources with a single policy, which reduces the overall number of policies that you need to manage.
{: tip}

## Step 2. Invite users 
{: #step1}

You can invite one or multiple users in a single invite. If you invite multiple users in one invitation, the same access is assigned to each user. However, you can invite users to your account with no access, and assign them access later.

1. Go to **Manage** &gt; **Access (IAM)**, and select **Users**.
2. Click **Invite users**.
3. Enter the email addresses of the users that you want to invite.
4. (Optional) If you already have access groups set up, click **Add** in the row of the access group to which you want to add the users.
5. (Optional) Expand the **Manually assign users access** section if you want to assign Cloud Foundry roles, classic infrastructure permissions, individual IAM service or resource policies, or account management access.
  1. Select the tile for the type of access to assign, and follow the prompts to define the scope of access. Select all roles that apply.
  
  Click the **Actions for role** option to view a list of all actions that are mapped to a specific role. 
  {: tip}
  
  2. Click **Add** to save the access assignment.
6. After you add all the necessary access and you're ready to send the invitation, Click **Invite**.

For more information, see [Inviting users to an account](/docs/iam?topic=iam-iamuserinv#iamuserinv).


## Step 3. Manage access for existing users
{: #user_access_manage}

After you invite users, you might want to assign more access or edit the initial access that you assigned to ensure all users and access groups in your account have the correct level of access.

### Assigning new access
{: #new_access}

To assign a new access policy, complete the following steps:

1. From the menu bar, click **Manage** &gt; **Access (IAM)**, and select **Users**.
2. Select the name of the user that you want to assign access.
3. Click **Access policies**.
4. Click **Assign access**.
5. Choose how you want to assign access:
    * Select **Assign access within a resource group** to assign access to all resources within a group or to just resources for a specific service within a group. You can also provide the user with access to view, edit, or manage access to the resource group by selecting a role for access to the resource group. 
    
  Assign the Viewer role or higher for the resource group that contains the resource to ensure that the user can access the     resource from the Resource list page.
  {:tip}
    
    * Select **Assign access to resources** to assign access to all Identity and Access enabled resources across the account, all resources of a specific service across the account, a single instance, or a single resource within a specific service instance.
    * Select **Assign access to Account management services** to assign access to all account management services or just one account management service.
    
6. Select any combination of roles or permissions to define the scope of access. For more information, see [Cloud IAM roles](/docs/iam?topic=iam-iamusermanrol#iamusermanrol).
7. Click **Assign**.


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

Learn what else you can do with {{site.data.keyword.Bluemix_notm}} IAM by checking out the [Cloud IAM features](/docs/iam?topic=iam-iamoverview#features) list.
