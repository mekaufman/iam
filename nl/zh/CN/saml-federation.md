---

copyright:

  years: 2019

lastupdated: "2019-07-02"

keywords: federated ID, enterprise SSO, SAML federation

subcollection: iam

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:tip: .tip}
{:new_window: target="_blank"}
{:deprecated: .deprecated}
    
# 管理不推荐的 SAML 联合
{: #saml-federation}

如果先前在 SoftLayer 客户门户网站中使用 SAML 身份提供者设置了联合，那么可以在 {{site.data.keyword.Bluemix}} 控制台的“身份提供者”页面中编辑身份提供者配置数据或将其删除。
{: shortdesc}

不推荐使用此类型的联合。如果删除此配置，那么将是永久性的且无法再次设置。现在，您可以利用与 IBM 标识的联合。有关更多信息，请参阅[使用联合标识注册](/docs/account?topic=account-signup#signup-federated)。
{: deprecated}

要编辑 SAML 配置数据，请完成以下步骤：

1. 转至**管理** > **访问权 (IAM)**，然后选择**身份提供者**。 
2. 单击**编辑**。
3. 更改需要编辑的字段中的信息。
4. 单击**保存**。

要删除不推荐的 SAML 联合配置，请完成以下步骤：

1. 转至**管理** > **访问权 (IAM)**，然后选择**身份提供者**。 
2. 单击**删除**。
3. 选择选项以确认您了解删除配置是永久性的。因为不推荐此类型的联合，因此无法再次设置。
4. 单击**删除**。

