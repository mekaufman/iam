---

copyright:

  years: 2017, 2019

lastupdated: "2019-05-14"

keywords: SoftLayer permissions, classic infrastructure access, classic infrastructure permission, migrated SoftLayer permissions, migrated permission access group

subcollection: iam

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:important: .important}
{:new_window: target="_blank"}

# 经典基础架构许可权
{: #infrapermission}

邀请用户加入您的帐户时，可以从三个用于分配批量访问权的经典基础架构许可权集内进行选择：仅查看、基本用户和超级用户。
{:shortdesc}

您邀请某人加入帐户时，只有您（即帐户所有者）或具有“管理用户”经典基础架构许可权的用户可以调整用户的许可权。如果您不是帐户所有者，那么只能分配已为您分配的许可权级别或许可权子集。帐户所有者可以更新帐户中任何人的许可权，使其具有任何访问级别。



在用户接受邀请后，可以设置额外许可权。例如，在邀请时分配的初始许可权集并未授予对设备的访问权。因此，在用户接受邀请后，您必须授予设备访问权。有关更多信息，请参阅[管理经典基础架构访问权](/docs/iam?topic=iam-mngclassicinfra#mngclassicinfra)。

下图显示了如何为每个用户分配经典基础架构许可权。您可以通过从颗粒度许可权选项进行选择来授予每个用户对经典基础架构服务或设备的访问权，从而定制每个用户的访问权。

![经典基础架构访问权](images/ClassicIaaS.svg "通过选择用户、设备或服务，然后选择细颗粒度许可权的任意组合，从而分配经典基础架构访问权")



## 迁移的经典基础架构许可权
{: #predefined}

现在，用于查看和管理帐单信息以及使用支持案例的一组经典基础架构许可权已迁移到访问组。帐户中先前分配了这些许可权的用户现在已分配给相应的已迁移许可权访问组。因此，可以使用 IAM 访问策略直接管理经典基础架构许可权。有关迁移的许可权和用于每个许可权的访问组的更多信息，请参阅[管理迁移的 SoftLayer 帐户许可权](/docs/iam?topic=iam-migrated_permissions)。
