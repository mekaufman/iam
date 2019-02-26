---

copyright:

  years: 2018, 2019
lastupdated: "2019-01-30"

keywords: access groups, access group, create group, assign access to group

subcollection: iam

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:tip: .tip}
{:note: .note}


# Setting up access groups
{: #groups}

An access group can be created to organize a set of users and service IDs into a single entity that makes it easy for you to assign access. You can assign a single policy to the group instead of assigning the same access multiple times per individual user or service ID.
{:shortdesc}

To manage or create new access groups, you must be the account owner, administrator or editor on the IAM Access Groups service in the account, or the assigned administrator or editor for the all Account Management Services. Additionally, an administrator or editor can be assigned access to manage an individual group by creating an access policy where the resource is the Access Group ID. For more information about access policies and roles for the IAM Access Groups service, see [IAM access](/docs/iam?topic=iam-userroles#userroles).

To make assigning and managing access even easier, you can set up resource groups to organize a set of resources that you want a group of users to have access to. When your resource group is set up, you can assign a policy giving access to all resources within that group instead of creating access policies for individual service instances within your account.
{: tip}

## Creating an access group
{: #create_ag}

To create an access group, complete the following steps:

1. From the menu bar, click **Manage** &gt; **Access (IAM)**, and select **Access Groups**.
2. Click **Create**.
3. Enter a name and optional description for your group, and click **Create**.

Next, continue to set up your group by adding users or service IDs:

1. Select the name of the group that you want to add to.
2. Click **Add users** on the **Users** tab.
3. Select the users that you want to add from the list, and click **Add to group**.
4. To add service IDs to the group, click the **Service IDs** tab, and click **Add service ID**.
5. Select the IDs that you want to add from the list, and click **Add to group**.

You can delete a group by selecting the **Remove group** option. When you remove a group from the account, you are removing all users and service IDs from the group and all access that is assigned to the group.
{: note}

To create an access group by using the CLI, you can use the [ibmcloud iam access-group-create](/docs/cli/reference/ibmcloud?topic=cloud-cli-ibmcloud_commands_iam#ibmcloud_iam_access_group_create) command.
```
ibmcloud iam access-group-create GROUP_NAME [-d, --description DESCRIPTION]
```
{: codeblock}


## Assigning access to a group
{: #access_ag}

After you set up your group with users and service IDs, you can assign a common access policy to the group. Remember, any policy that you set for the group applies to all entities within the group.

1. From the menu bar, click **Manage** &gt; **Access (IAM)**, and select **Access Groups**.
2. Select the name of the group that you want to assign access to.
3. Click **Access policies**.
4. Click **Assign access**.
5. Choose to assign access by resources within a resource group, individual resources available within the account, or account management services.

To create an access group policy by using the CLI, you can use the [ibmcloud iam access-group-policy-create](/docs/cli/reference/ibmcloud?topic=cloud-cli-ibmcloud_commands_iam#ibmcloud_iam_access_group_policy_create) command.
```
ibmcloud iam access-group-policy-create GROUP_NAME {-f, --file @JSON_FILE | --roles ROLE_NAME1,ROLE_NAME2... [--service-name SERVICE_NAME] [--service-instance SERVICE_INSTANCE] [--region REGION] [--resource-type RESOURCE_TYPE] [--resource RESOURCE] [--resource-group-name RESOURCE_GROUP_NAME] [--resource-group-id RESOURCE_GROUP_ID]}
```
{: codeblock}
