---

copyright:

  years: 2019

lastupdated: "2019-05-13"

keywords: migrated permissions, SoftLayer account permissions, migrated permission access group, migrated classic infrastructure permissions

subcollection: iam

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:important: .important}
{:new_window: target="_blank"}


# 管理迁移的 SoftLayer 帐户许可权
{: #migrated_permissions}

现在，访问组包括一组迁移的 SoftLayer 帐户许可权，用于查看和管理帐单信息以及使用支持案例。帐户中先前分配了这些许可权的用户现在已分配给相应的已迁移许可权访问组。因此，可以使用 IAM 访问组直接管理许可权。
{:shortdesc}

这些特殊访问组包含所有相应的 IAM 策略，以保留 SoftLayer 帐户许可权的原始行为。例如，要使某个用户能够继续查看支持案例上所有用户的所有更新，提供“开具凭单”SoftLayer 帐户许可权的已迁移许可权访问组会包含一个额外的 IAM 策略，用于分配对用户管理服务的“查看者”角色。有关更多信息，请参阅[分配用于处理支持案例的用户访问权](/docs/get-support?topic=get-support-access#access)。

通过在迁移的许可权访问组中添加和除去用户的已迁移经典基础架构许可权，可以继续直接通过 IAM 来管理这些许可权。这些访问组具有的策略已锁定，以保留其成员的访问行为。要保持针对新 IAM 用户的易用性，请避免删除这些访问组。

迁移经典基础架构许可权后，必须停止使用这些许可权。请参阅下表，以了解所有迁移的经典基础架构许可权（现在这些许可权属于 IAM 访问组）。
{: important}

|迁移的许可权访问组名称|允许的操作|
|----------|---------|
|查看帐户摘要|查看帐户摘要页面以及发票和付款。|
|获取一致性报告|请求合规性报告。|
|编辑公司概要文件|编辑公司概要文件信息。|
|一次性付款|在用户的帐户中一次性付款。|
|更新付款详细信息|更新周期性每月付款信息。|
|设置欧盟案例限制|启用或禁用用于将支持案例数据限制为欧盟的“欧盟支持”选项。|
|添加案例和查看订单|创建支持案例和查看所有订单|
|编辑案例|编辑任何支持案例。|
|搜索案例|搜索所有支持案例（如果同时分配了“查看案例”许可权）。|
|查看案例|查看所有支持案例。|
{: caption="表 1. 预定义的访问组" caption-side="top"}

