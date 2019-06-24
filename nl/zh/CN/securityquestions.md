---

copyright:

  years: 2018, 2019

lastupdated: "2019-05-01"

keywords: security questions, MFA, multifactor authentication, login security

subcollection: iam

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:tip: .tip}
{:note: .note}

# 为用户启用 MFA 安全问题
{: #questions}

作为具有正确访问权的管理员，您可以为用户启用登录时提示该用户输入安全问题和答案的选项。仅对于启用了此设置的帐户，才需要此类型的多因子认证 (MFA)。仅对于启用了与基于标识的 MFA 不同的设置的帐户，才需要此类型的多因子认证 (MFA)。有关更多信息，请参阅[多因子认证的类型](/docs/iam?topic=iam-types#types)。
{:shortdesc}

如果您具有以下任一类型的访问权，那么可以为帐户中的其他用户更新此设置：

* 对用户管理服务的编辑者或更高角色
* 您在经典基础架构层次结构中是用户的祖代，并且分配有“管理用户”经典基础架构许可权。


要为用户开启此 MFA 选项，该用户必须在概要文件的“登录设置”页面中设置[安全问题](/docs/account?topic=account-login-settings#security-questions)和答案。
{: note}

1. 在菜单栏中，单击**管理** &gt; **访问权 (IAM)**，然后选择**用户**。
2. 从列表中选择用户。
3. 在**管理用户登录**部分的**用户详细信息**页面中，将**登录时需要 MFA 安全问题**选项设置为开启。

如果您在“用户详细信息”页面上启用了“用户管理的登录设置”，那么您可以自行管理此设置。
{: tip}
