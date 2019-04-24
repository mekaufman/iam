---

copyright:

  years: 2018, 2019

lastupdated: "2019-01-28"

keywords: parent user, change parent user, classic infrastructure hierarchy

subcollection: iam

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:tip: .tip}

# 更新用户的父用户
{: #update-parent}

如果您具有正确的访问权，那么可以更新用户的父代。“用户列表可视性设置”设置为“受限”时，更新父用户会影响用户查看帐户中其他用户的情况。用户只能看到自己是其父代的其他用户，以及父用户的那些后代所邀请的其他任何用户。
{:shortdesc}

有关此设置的更多详细信息，请参阅[用户列表可视性设置](/docs/iam?topic=iam-userlistview#userlistview)。

如果您具有以下访问权，那么可以更新其他用户的父代：

* 具有对用户管理服务的编辑者或更高角色的 IAM 策略。
* 您在经典基础架构层次结构中是用户的祖代，并且分配有“管理用户”经典基础架构许可权。


要更新用户的父代，请完成以下步骤：

1. 在菜单栏中，单击**管理** &gt; **访问权 (IAM)**，然后选择**用户**。  
2. 从列表中选择用户名。
3. 在“用户详细信息”页面中，从**父代**菜单中选择新的父用户。
4. 单击**应用**。
