---

copyright:

  years: 2018, 2019

lastupdated: "2019-01-30"

keywords: MFA, multifactor authentication, external authentication, order authentication, Symantec, phone-based authentication, cancel authentication order

subcollection: iam

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:tip: .tip}

# 为用户订购外部认证 MFA
{: #external}

作为具有正确访问权的管理员，您可以订购外部认证，并为用户登录启用多因子认证 (MFA) 选项。外部认证选项会按月向您收费。仅对于启用了与基于标识的 MFA 不同的设置的帐户，才需要此类型的多因子认证 (MFA)。有关更多信息，请参阅[多因子认证的类型](/docs/iam?topic=iam-types#types)。
{:shortdesc}

## 订购外部认证
{: #ordering}

如果您具有以下任一访问权，那么可以为用户订购外部认证：

* 对用户管理服务的编辑者或更高角色
* 您在经典基础架构层次结构中是用户的祖代，并且分配有“管理用户”经典基础架构许可权。

要订购外部认证，请完成以下步骤：

1. 在菜单栏中，单击**管理** &gt; **访问权 (IAM)**，然后选择**用户**。
2. 从列表中选择用户。
3. 在**用户详细信息**页面的“管理用户登录”部分中，选择**订购外部认证**。
4. 选择 **Symantec Identity Protection** 或**基于电话的身份保护**。
    * 对于 Symantec 认证，用户必须下载 [Symantec VIP ](https://vip.symantec.com/){: new_window}![外部链接图标](../icons/launch-glyph.svg) 应用程序，并获取凭证标识才能继续执行订购过程。
    * 对于基于电话的认证，您可以继续执行订单，但您的用户必须[设置用户配置](/docs/account?topic=account-third-party-MFA#third-party-MFA)，然后您才能启用此选项。
5. 根据您的选择，遵循提示来复查价格和条款，然后下单。
6. 单击**订购**以最终完成您的选择。

订购 Symantec 认证后，可以在“用户详细信息”页面中为用户开启此选项。订购基于电话的认证并且用户对其进行配置后，您可以在“用户详细信息”页面中为该用户开启此选项。

## 禁用外部认证选项
{: #disable}

您可以随时为用户禁用 Symantec 或基于电话的 MFA。

1. 在菜单栏中，单击**管理** &gt; **访问权 (IAM)**，然后选择**用户**。
2. 从列表中选择用户。
3. 在**用户详细信息**页面中，将 **Symantec 认证**或**基于电话的认证**选项设置为关闭。

## 取消外部认证选项
{: #cancel}

如果您具有正确的访问权，那么可以随时取消对外部认证的订购。您可以选择立即取消而没有任何退款，也可以选择在订购满一年时取消。

要取消对外部认证的订购，您必须是帐户所有者或具有以下所有访问权：

* “管理用户”经典基础架构许可权
* “取消服务”经典基础架构许可权
* 支持中心帐户管理服务的管理员，或具有在[迁移的许可权访问组](/docs/iam?topic=iam-predefined#predefined)内不可用的“查看”、“编辑”和“开具凭单”已迁移经典基础架构许可权。

要取消外部认证订购，请完成以下步骤：

1. 在菜单栏中，单击**管理** &gt; **访问权 (IAM)**，然后选择“用户”。
2. 从列表中选择用户。
3. 在**用户详细信息**页面中，针对 **Symantec 认证**或**基于电话的认证**行（根据您订购的项），单击**删除** ![“删除”图标](../icons/icon_trash.svg)。
4. 选择何时将其除去。
5. 单击**除去**。
