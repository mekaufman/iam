---

copyright:

  years: 2015, 2019
lastupdated: "2019-01-30"

keywords: service ID, service ID access, managing access for service IDs

subcollection: iam

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:tip: .tip}
{:note: .note}

# Managing service ID access policies
{: #serviceidpolicy}

When you create a service ID, you can assign service policies for that service ID to control the level of access that is allowed when it's used to authenticate with your services. You can update these assigned access policies at any time by changing an existing policy, deleting a policy, or assigning a new one.
{:shortdesc}

If you delete or edit an existing policy for a service ID currently being used, it might cause service interruption.
{: note}

## Assigning new access
{: #access_new}

To assign access to all resources in a resource group or to just one service within a resource group, complete the following steps:

1. From the menu bar, click **Manage** &gt; **Access (IAM)**, and select **Service IDs**.
2. Select the service ID from the table that you want to assign a service policy for.
3. Click **Access policies**.
4. Click **Assign access**.
5. Select to **Assign by resource group**.
6. Select a resource group.
7. Choose a role for the **Assign access to resource group** field. This option allows the user to view the resource group on their resource list, edit the resource group name, or manage user access to the group. You can select **No access**, if you want the user to have access to only the resource that you specify and not the group that it's assigned to.
8. Select a service within the resource group, or select to provide access to all services within the selected group.
9. Choose any combination of roles to assign the wanted access for the user. This access applies only to the resources that you selected for the policy. It doesn't give access to the actual container that is the resource group.
10. Select **Assign**.

To assign access to an individual resource in the account, complete the following steps:

1. From the menu bar, click **Manage** &gt; **Access (IAM)**, and select **Service IDs**.
2. Select the service ID from the table that you want to assign a service policy for.
3. 3. Click **Access policies**.
4. Click **Assign access**.
5. Select to **Assign by resource**.
6. Select a service.
7. Select **All current regions** or a specific region, if your are prompted.
8. Select **All current service instances** or select a specific service instance.
9. Depending on the service that you selected, you might see the following fields. If you don't enter values for these fields, the policy is assigned at the service instance level instead of the bucket level.
    * **Resource type**: Enter **bucket**.
    * **Resource ID**: Enter the name of your bucket.
10. Choose any combination of roles to assign the wanted access for the user.
11. Select **Assign**.

To assign access to an individual account management services or all account management services, complete the following steps:

1. From the menu bar, click **Manage** &gt; **Access (IAM)**, and then select **Service IDs**.
2. Select the service ID from the table that you want to assign a service policy for.
3. Click **Access policies**.
4. Click **Assign access**.
5. Select to assign access to **Account Management Services**
6. Select **All Account Management Services** or select a specific account management service.
7. Select any combination of roles to assign the wanted access.

You might receive a message that a policy exists for the details that you've selected. If a policy with the exact details and roles is being created, you're prompted to make changes to the new policy since duplicate policies aren't allowed. If you're creating a policy with the same details but different role assignments as an existing policy, you're prompted to review and update the existing policy with the role assignments that you want to assign.
{: tip}

## Editing existing access
{: #access_edit}

To edit an existing policy:

1. From the menu bar, click **Manage** &gt; **Access (IAM)**, and select **Service IDs**.
2. Select the service ID from the table that you want to edit a service policy for.
3. Click **Access policies**.
4. Identify the row of the policy that you want to edit, and select **Edit policy** from the **Actions** ![List of actions icon](../icons/action-menu-icon.svg) menu.
5. Make your changes, and then save the policy.

To update a service policy by using the CLI, you can use the [ibmcloud iam service-policy-update](/docs/cli/reference/ibmcloud?topic=cloud-cli-ibmcloud_iam_user_policy_update#ibmcloud_iam_service_policy_update) command.
```
ibmcloud iam service-policy-update SERVICE_ID POLICY_ID [-v, --version VERSION] {--file JSON_FILE | [-r, --roles ROLE_NAME1,ROLE_NAME2...] [--service-name SERVICE_NAME] [--service-instance SERVICE_INSTANCE] [--region REGION] [--resource-type RESOURCE_TYPE] [--resource RESOURCE] [--resource-group-name RESOURCE_GROUP_NAME] [--resource-group-id RESOURCE_GROUP_ID]} [-f, --force]",
```
{: codeblock}

When you edit access for a service ID, you might receive a message about not allowing duplicate policies. If you're editing an existing policy and the changes you make are in conflict with access that is already assigned, you can choose to change the policy you're currently editing to provide different access, or you can go to the existing policy it is in conflict with to review and make changes if needed. You might want to delete the policy you're editing, if a duplicate policy exists that meets your needs.
{: tip}

## Removing access
{: #access_remove}

To remove an existing policy:

1. From the menu bar, click **Manage** &gt; **Access (IAM)**, and select **Service IDs**.
2. Select the service ID from the table that you want to delete a service policy for.
3. Click **Access policies**.
4. Identify the row of the policy that you want to delete, and select **Remove** from the **Actions** ![List of actions icon](../icons/action-menu-icon.svg) menu.
5. Review the details of the policy that you're about to remove, and then click **Remove** to confirm.

To delete a service policy by using the CLI, you can use the [ibmcloud iam service-policy-delete](/docs/cli/reference/ibmcloud?topic=cloud-cli-ibmcloud_iam_user_policy_update#ibmcloud_iam_service_policy_delete) command.
```
ibmcloud iam service-policy-delete SERVICE_ID POLICY_ID [-f, --force]
```
{: codeblock}
