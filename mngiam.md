---

copyright:

  years: 2017, 2019

lastupdated: "2019-09-20"

keywords: resource access, assign access, IAM access policy, access to resource groups, edit access, remove access 

subcollection: iam

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:tip: .tip}
{:note: .note}

# Managing access to resources
{: #iammanidaccser}

To manage access or assign new access for users by using IAM policies, you must be the account owner, administrator on all services in the account, or the assigned administrator for the particular service or service instance. For more information about access policies and roles, see [IAM access](/docs/iam?topic=iam-userroles#userroles).
{:shortdesc}

## Editing existing access
{: #edit_existing}

1. From the menu bar, click **Manage** &gt; **Access (IAM)**, and select **Users**.
2. Select the name of the user that you want to assign access.
3. From the row for the policy that you want to edit, select the **Actions** ![List of actions icon](../icons/action-menu-icon.svg) menu, and then click **Edit policy**.
4. Edit the policy.
5. Click **Save**.

To update a user policy by using the CLI, you can use the [**`ibmcloud iam user-policy-update`**](/docs/cli/reference/ibmcloud?topic=cloud-cli-ibmcloud_commands_iam#ibmcloud_iam_user_policy_update) command.
```
ibmcloud iam user-policy-update USER_NAME POLICY_ID [-v, --version VERSION] {-f, --file JSON_FILE | [--roles ROLE_NAME1,ROLE_NAME2...] [--service-name SERVICE_NAME] [--service-instance SERVICE_INSTANCE] [--region REGION] [--resource-type RESOURCE_TYPE] [--resource RESOURCE] [--resource-group-name RESOURCE_GROUP_NAME] [--resource-group-id RESOURCE_GROUP_ID]}
```
{: codeblock}

## Assigning new access
{: #assign_new_access}

You can assign access to resources by using two types of policies:

* Access to resources within a resource group, including the option for just one or all
* Access to resources in the account, including the option for just one type or all types

If you want to enable a user full administrator access to complete [account management tasks](/docs/iam?topic=iam-account-services#account-services), such as inviting and removing users, viewing billing and usage, managing service IDs, managing access groups, managing user access, and access to all account resources, you must create two policies: one on **All Identity and Access enabled services** with the Administrator and Manager roles and one on **All Account Management Services** with the Administrator role and the Administrator role for all resource groups in the account.
{: tip}

### Access to resources within a resource group
{: #access_to_resources}

To assign access to all resources in a resource group or to just one service within a resource group, complete the following steps:

1. From the menu bar, click **Manage** &gt; **Access (IAM)**, and select **Users**.
2. From the row for the user that you want to assign access, select the **Actions** ![List of actions icon](../icons/action-menu-icon.svg) menu, and click **Assign access**.
3. Select **Assign access within a resource group**.
4. Select a resource group.
5. Choose a role for the **Assign access to a resource group** field to enable the user to view the resource group in their resource list, edit the resource group name, or manage user access to the group. The Viewer role or higher is required to enable the user to view and access the resource in the console.
6. Select a service within the resource group, or select to provide access to all services within the selected group.
7. Choose any combination of roles to assign to the user. This access applies only to the resources that you selected for the policy. It doesn't give access to the actual container that is the resource group.
8. Click **Assign**.

### Access to resources
{: #resourceaccess}

To assign access to an individual resource in the account or access to all resources in the account, complete the following steps:

1. From the menu bar, click **Manage** &gt; **Access (IAM)**, and select **Users**.
2. From the row for the user that you want to assign access, select the **Actions** ![List of actions icon](../icons/action-menu-icon.svg) menu, and click **Assign access**.
3. Select **Assign access to resources**.
4. Select a service or select **All Identity and Access enabled services**.
5. Select **All current regions** or a specific region if your are prompted.
6. Select **All current service instances** or select a specific service instance.
7. Depending on the service that you selected, the following fields might be displayed. If you don't enter values for these fields, the policy is assigned at the service instance level instead of the bucket level.
    * **Resource type**: Enter `bucket`.
    * **Resource ID**: Enter the name of your bucket.
8. Choose any combination of roles to assign to the user.
9. Click **Assign**.

If the user doesn't have a role on the resource group that contains the resources, they can't access the resources from the resource list in the account to start working with them. Assign the Viewer role or higher on the resource group itself to ensure a user can access the resource.
{: note}

## Removing access
{: #removing_access}

1. From the menu bar, click **Manage** &gt; **Access (IAM)**, and select **Users**.
2. Select the user name that you want to remove access for.
3. From the **Access policies** tab, select the **Actions** ![List of actions icon](../icons/action-menu-icon.svg) menu on the row for the policy you want to remove, and click **Remove**.  
4. Review the user policy details that you're about to remove, and confirm by clicking **Remove**.

To remove a user policy by using the CLI, you can use the [**`ibmcloud iam user-policy-delete`**](/docs/cli/reference/ibmcloud?topic=cloud-cli-ibmcloud_commands_iam#ibmcloud_iam_user_policy_delete) command.
```
ibmcloud iam user-policy-delete USER_ID POLICY_ID [-f, --force]
```
{: codeblock}

## Reviewing your assigned access
{: #review_your_access}

If you need to review your assigned access in an account that you've been added to, complete the following steps:

1. From the menu bar, click **Manage** &gt; **Access (IAM)**, and select **Users**.
3. Select your name.
4. Review your assigned access in the **Access policies** section.

If you need more access, you must contact the account owner to update your access or contact the administrator for the service or service instance to update the access policy.
