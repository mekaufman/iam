---

copyright:

  years: 2017, 2019

lastupdated: "2019-01-28"

keywords: classic infrastructure access, VPN subnet access, classic infrastructure permissions, device access

subcollection: iam

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:tip: .tip}
{:note: .note}
{:deprecated: .deprecated}

# Managing classic infrastructure access
{: #mngclassicinfra}

You can update permissions for classic infrastructure services or add device and VPN subnet access for a user at any time. To access the classic infrastructure permissions, go to **Manage** &gt; **Access (IAM)**, select **Users**. Then, select the user's name that you want to update access for, and click **Classic infrastructure**.
{:shortdesc}

You must be assigned the Manage users classic infrastructure permission and be an ancestor of the user within the classic infrastructure user hierarchy. Account owners have full access to the account, so they do not see the permissions on the page. Individual users can't edit their own permissions, and they also don't see permissions on the page.
{: note}

  1. Select **Permissions** to update the user's permissions. You can select from four types of permissions: account, devices, network, and services. Individually select permissions from each category, or use a permission set option to assign permissions in bulk.

    The account management and support permissions that you previously assigned to users in your account are now migrated from classic infrastructure permissions to migrated IAM access groups. For more information, see [Migrated classic infrastructure permissions](/docs/iam?topic=iam-migrated_permissions).
    {: tip}

  2. To grant a user device access, select **Devices**, and assign the access to specific devices and device types as needed.

    Access to devices is assigned after the user is invited to the account. The device permissions apply to the specific devices that are assigned for the user. You can select specific devices from the list, or you can assign access by device type. If you assign access by device type, you might want to use the **Enable future access** options to ensure that each time new devices of a specific type are added, the user automatically gets assigned access to those devices.

  3. To update a user's access to VPN subnets, select **VPN subnets**.

    Use the **Auto-assign** option to set how the user gets access to VPN subnets based on their device access. If this option is set to on, the user is automatically assigned access to all subnets for the devices they already have access to. You can set this option to off to manually select subnets from the list.
    {: tip}

    To provide access to VPN subnets, the user must already be assigned access to one or more devices. If the user does not access to any devices, no subnets are available for selection. You can define the type of VPN subnets that the user has access to by using the **VPN type** option. If you select **None**, no VPN access can be assigned.

    The PPTP option is deprecated, so if you have this option and clear it, it is no longer available.
    {: deprecated}
