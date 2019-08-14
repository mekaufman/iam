---

copyright:

  years: 2018, 2019

lastupdated: "2019-08-08"

keywords: remove user, delete user

subcollection: iam

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:tip: .tip}

# 从帐户中除去用户
{: #remove}

从帐户中除去用户后，该用户即无法再登录到控制台，无法切换到您的帐户（如果他们仍然属于其他帐户），也无法访问帐户资源。
{:shortdesc}

只有帐户所有者或具有以下访问权的用户可以从帐户中除去用户：

* 必须有一个 IAM 策略来分配对用户管理帐户管理服务的“管理员”角色，并且必须是 Cloud Foundry 组织管理者（如果用户属于 Cloud Foundry 组织）。
* 如果您的帐户中具有经典基础架构，那么用户必须有一个 IAM 策略来分配对用户管理帐户管理服务的“管理员”角色，必须是 Cloud Foundry 组织管理者（如果用户属于 Cloud Foundry 组织），并且必须是经典基础架构用户层次结构中具有“管理用户”经典基础架构许可权分配的用户的祖代。

要从帐户除去用户，请完成以下步骤：

1. 在菜单栏中，单击**管理** &gt; **访问权 (IAM)**，然后选择**用户**。
2. 在要除去的用户所在的行中，从**操作** ![“操作列表”图标](../icons/action-menu-icon.svg) 菜单中，选择**除去用户**。

该用户创建的所有资源都会保留在帐户中。但该用户不再有权使用那些资源，所以该服务或服务实例的帐户所有者或管理员可以分配其他用户使用那些资源，也可以将资源从帐户中删除。

如果您收到错误消息，提示无法除去经典基础架构用户，那么请确保该用户在用户层次结构中的所有后代都[已分配新父代](/docs/iam?topic=iam-update-parent)，[在帐户中已禁用](/docs/iam?topic=iam-status)或已删除，然后重试。
{: tip}
