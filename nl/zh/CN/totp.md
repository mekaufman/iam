---

copyright:

  years: 2018, 2019

lastupdated: "2019-01-30"

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:tip: .tip}
{:note: .note}

# 为用户启用一次性密码 MFA
{: #totp}

作为具有正确访问权的管理员，您可以在 {{site.data.keyword.Bluemix}} 控制台的“用户详细信息”页面中，为用户启用登录时提示该用户输入基于时间的一次性密码 (TOTP) 的选项。仅对于启用了与基于标识的 MFA 不同的设置的帐户，才需要此类型的多因子认证 (MFA)。有关更多信息，请参阅[多因子认证的类型](/docs/iam?topic=iam-types#types)。
{:shortdesc}

如果您具有以下任一访问权，那么可以为帐户中的其他用户更新此设置：

* 对用户管理服务的编辑者或更高角色
* 您在经典基础架构层次结构中是用户的祖代，并且分配有“管理用户”经典基础架构许可权。

要为用户开启此登录设置以提示该用户输入 TOTP MFA，请完成以下步骤。

要为用户开启此 MFA 选项，该用户必须首先在概要文件的“登录设置”页面中[设置 TOTP](/docs/account?topic=account-MFA#MFA)。
{: note}

1. 在菜单栏中，单击**管理** &gt; **访问权 (IAM)**，然后选择**用户**。
2. 从列表中选择用户。
3. 在**管理用户登录**部分的**用户详细信息**页面中，将**基于时间的一次性密码 MFA** 选项设置为开启。

如果您在“用户详细信息”页面上启用了“用户管理的登录设置”，那么您可以自行管理此设置。
{: tip}

