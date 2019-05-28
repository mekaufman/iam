---

copyright:

  years: 2015, 2019
lastupdated: "2019-01-28"

keywords: invite, invite users, invitation access, vpn-only user

subcollection: iam

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:tip: .tip}
{:note: .note}

# Inviting users
{: #iamuserinv}

You can invite users, cancel invitations, and resend a pending invitation to an invited user. In addition, you can invite a single user or multiple users at once.    
{:shortdesc}

To invite users and manage outstanding invitations, you must be either an account owner, an organization manager, a user with an IAM access policy with Editor or higher role on the user management service, or you must have classic infrastructure permissions to add users.

## Setting up an invitation
{: #invitations}

To invite users or manage user invitations in your account, complete the following steps:

1. From the menu bar, click **Manage** &gt; **Access (IAM)**, and select **Users**.
2. Click **Invite users**.
3. Specify the email address of the user. If you are inviting more than one user with a single invitation, they are all assigned the same access.
4. Add one or more of the access options that you manage. You must assign at least one access option. For any additional access options that you don't add and configure, the default value of **no access** is assigned. You might see one or all of the following access options, depending on the options that you are authorized to manage:

  * **Services**
  * **Cloud Foundry access**
  * **Classic infrastructure access**.

  For more information, see [Assigning user access](/docs/iam?topic=iam-iamuserinv#assignaccess).

If you determine that a user does not need access, you can cancel an invitation for any users that are shown in a **Processing** or **Pending** state in the **Status** column. If an invited user did not receive an invitation, you can resend the invitation to any user in a **Pending** state.

If you want to invite users by using the command-line interface (CLI), see the [ibmcloud account user-invite](/docs/cli/reference/ibmcloud?topic=cloud-cli-ibmcloud_account_user_invite#ibmcloud_account_user_invite) command.
{: tip}

## Assigning user access from an invitation
{: #assignaccess}

You assign access for users as you invite them by assigning {{site.data.keyword.Bluemix}} IAM policies, Cloud Foundry access, and classic infrastructure permissions. Depending on the access options that you are authorized to manage, you can invite and provide access for users across the account, resource groups, organizations, spaces, service instances, and classic infrastructure. The following sections describe the three types of access that you can assign to an invited user.

### Services
{: #invite_services}

You can assign access by creating an initial {{site.data.keyword.Bluemix_notm}} IAM access policy when you invite a new user. In the Services section, you can provide a user access to account management services, services in a resource group with access to manage the resource group, or to an individual resource in the account.

After the user accepts the invitation, you can assign additional access. See [Managing access to resources](/docs/iam?topic=iam-iammanidaccser#iammanidaccser) for details on editing policies to add extra roles, assigning more access, or removing a policy for a user.

Depending on which service you select when you assign the policy, you might not see all of fields that are described in the following procedures.
{: note}

#### Account management services access
{: #invite_acct_mgmt}

To delegate some of your responsibilities as an account owner, you can provide a user access to account management services. For example, you can delegate the ability to view billing and usage, invite and remove users, manage access groups, or manage service IDs. You can provide access to all account management services or just one.

1. From the **Invite users** screen, expand the **Services** section.
2. Select to assign access to **account management services**
3. Select **All account management services** or select a specific account management service.
4. Select any combination of roles to assign the wanted access.

#### Resource group access
{: #invite_rgs}

You can assign access to all services within a resource group or a single service type in a resource group.

1. From the **Invite users** screen, expand the **Services** section.
2. Select to assign access to resources in a **Resource group**.
3. Choose a resource group.
4. Choose a role for the **Assign access to a resource group** field to enable the user to view the resource group on the resource list, edit the resource group name, or manage user access to the group. You can select **No access**, if you want the user to be able to access only the resource that you specify and not the group that it is organized in.
5. Select a service within the resource group, or select to provide access to all services within the selected group.
6. Select any combination of roles to assign the wanted access. This access applies only to the resources that you selected for the policy. It does not give access to the actual container that is the resource group.

#### Resource access
{: #invite_resources}

You can assign access to a single resource within your account down to the instance.

1. From the **Invite users** screen, expand the **Services** section.
2. Select to assign access to a **Resource**.
3. Select a service.
4. Select **All current regions** or a specific region, if your are prompted.
5. Select **All current service instances** or select a specific service instance.
6. Depending on the service that you selected, you might see the following fields. If you do not enter values for these fields, the policy is assigned at the service instance level instead of the bucket level.
    * **Resource type**: Enter `bucket`.
    * **Resource ID**: Enter the name of your bucket.
7. Select any combination of roles to assign the wanted access.

For more information about the roles that are used when you assign access, see [IAM access](/docs/iam?topic=iam-userroles#iamusermanrol).

### Cloud Foundry access
{: #invite_cf}

When you invite new users, you can choose to add the user to an organization in the account. If you add the user to an organization, you can assign him or her an organization role. Then, you choose to give the invited user access to any or all of the spaces in the selected organization with an assigned space role.

1. From the **Invite users** screen, expand the **Cloud Foundry access** section.
2. Select an organization to add the user to.
3. Select an organization role to define the level of access for the selected organization.
4. Optional: Select **Add organization role** to specify an extra role.
5. Select **All current regions** or a specific region.
6. Select **All current spaces** or a specific space.
7. Select a space role to define the level of access for the selected spaces.
8. Optional: Select **Add space role** to specify an extra role.

For more information about the roles that are used when you assign access, see [Cloud Foundry roles](/docs/iam?topic=iam-cfaccess#cfroles).

You can add a Cloud Foundry role by using the [ibmcloud account user-invite](/docs/cli/reference/ibmcloud?topic=cloud-cli-ibmcloud_account_user_invite#ibmcloud_account_user_invite) CLI command, but the console must be used to assign other access or permissions.
{: tip}

### Classic infrastructure access
{: #invite_classicinfra}

The permissions that are assigned are automatically limited to the subset of permissions that you have. You become the parent user of any user that you invite.

1. From the **Invite users** screen, expand the **Classic infrastructure access** section.
2. Select a permission set to assign predefined bulk permissions.

Access to devices is granted separately after the user is added. Go to the **Classic infrastructure** access option for a user in the console.
{: note}

For information about configuring access for users after they are added to your account, see [Managing classic infrastructure access](/docs/iam?topic=iam-mngclassicinfra#mngclassicinfra).

## Adding VPN-only users
{: #add-vpn-only}

As the account owner or a user with the Manage user classic infrastructure permission, you can add a VPN-only user.

1. From the **Users** page, click **Add VPN-only user**.
2. Enter the personal information details for the user.
3. Click **Save**.
