---

copyright:

  years: 2018, 2019

lastupdated: "2019-01-30"

keywords: user list visibility, users page setting, user view access, limit access to users list, user list access

subcollection: iam

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}

# 设置用户查看访问权
{: #userlistview}

作为 {{site.data.keyword.Bluemix}} 帐户所有者，您可以查看帐户中的所有用户，并定义用户可以如何查看帐户中的其他用户。
{:shortdesc}

选择**不受限制的视图**选项时，帐户中的任何用户都可以从 {{site.data.keyword.Bluemix_notm}} 控制台中的“用户”页面查看其他用户。选择**受限视图**选项时，用户限制为只能查看自己邀请的帐户中用户，与之共享 Cloud Foundry 组织的用户，或在经典基础架构用户层次结构中是其后代的用户，即他们邀请的用户或其某个后代邀请的用户。

缺省情况下，系统会为您的帐户设置“不受限制的视图”。要更新此设置，请完成以下步骤：

1. 在菜单栏中，单击**管理** &gt; **访问权 (IAM)**，然后选择**设置**。
2. 针对**用户列表可视性**设置，选择**受限视图**。
