---

copyright:

  years: 2018, 2019
lastupdated: "2019-01-28"

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:tip: .tip}

# Best practices for assigning access
{: #account_setup}

To streamline the access assignment process, you can take advantage of access groups to assign a minimal number of policies by giving the same access to all users and service IDs that belong to the same access group. Use these best practices to learn more about providing users access to resources, resource groups, and account management services.
{:shortdesc}

To ensure that your account is fully set up for success, check out [Best practices for setting up your account](/docs/account?topic=account-account_setup#account_setup) and [Best practices for organizing resources in resource groups](/docs/resources?topic=resources-bp_resourcegroups#bp_resourcegroups).
{: tip}

## What is a good access group strategy?
{: #rg_strategy}

An access group is a grouping of user and service IDs to which the same IAM access can be granted. You can assign a single policy to the group instead of assigning the same access multiple times per individual user or service ID.

Assuming you followed the [best practices for setting up your account](/docs/account?topic=account-account_setup#account_setup), a logical way to assign access is by creating one access group per wanted level of access. Then, you can map each access group to the previously created resource groups. For example, to control access to the `CustApp` project, you might create the following access groups:

* Auditor-Group
* Developer-Group
* Admin-Group

For the Auditor-Group, assign two access policies that grant viewer access to the `CustApp-Test` and the `CustApp-Prod` resource groups. For the Developer-Group, assign two access policies that grant editor access to the `CustApp-Dev` and `CustApp-Test` environments. For the Admin-Group, assign three access policies that grant administrator access to all three `CustApp` resource groups.

Though these suggestions are designed for a hypothetical scenario, you can configure the access group to resource group mapping as you see fit.

## Creating access groups
{: #access-group-setup}

To create an access group, complete the following steps: 

1. In the {{site.data.keyword.Bluemix}} console, click **Manage** &gt; **Access (IAM)**, and select **Access Groups**.
2. Click **Create**.
3. Enter the name and description for the group.
4. Click **Create**.

After you create an access group, you can add users and service IDs to the group.

## How IAM access policies provide access
{: #how_access}

A policy consists of a subject, target, and role. The subject in this case is the access group. The target is what you want the subject to access, such as a set of resources, a service instance, all services in the account, or all instances of a service. The role defines the level of access that is granted to a user.

The most commonly used roles are viewer, editor, and administrator. The viewer role provides the least amount of access for viewing instances and resource groups in an account. The editor role has more access for creating, editing, deleting, and binding service instances. The administrator role includes everything for working with a service instance and can assign access to others. However, there are two different categories of roles that you should consider: platform and service. For more information about the roles that can be assigned, see the [IAM Cloud roles](/docs/iam?topic=iam-iamusermanrol#iamusermanrol). 

## Assigning access to access groups
{: #assigning-access}

You can organize resources in a resource group and users and service IDs into an access group to make assigning access as simple as possible. After you set up each one, you can create access policies for the access groups to give users in your account access to the resources that you created.

1. Click **Manage** &gt; **Access (IAM)**, and select **Access Groups**.
2. Select the name of the access group that you want to assign access.
3. Select the **Access policies** tab, and then click **Assign access**. You have the following options for assigning access:

  * **Assign access to resources within a resource group**: Use this option to give the two-part policy that is needed for users who create resources from the catalog and assign the resources to a resource group. When you use this option, you can give access to the resource group itself, and all resources in a particular resource group or just one service or instance in the resource group.
  * **Assign access to resources**: Use this option to assign access to all IAM-enabled services across the account or to a single service in the account, but not to an instance level.
  * **Assign access to Account Management Services**: Use this option to provide a user access to account management services as a way to delegate some of your account owner capabilities. For example, you can delegate the ability to view billing and usage, invite and remove users, manage access groups, manage catalog services, or manage service IDs. You can provide access to all account management services or just one.

Easily give multiple users administrator access to everything in an account by creating an access group and assigning two policies to it. To create the first policy, use the **Assign access to resources** option, and select **All Identity and Access enabled services** with the administrator role assigned. To create the second policy, use the **Assign access to Account Management Services** option, and select **All Account Management Services** with the administrator role assigned.
{: tip}


