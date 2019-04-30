---

copyright:

  years: 2017, 2019

lastupdated: "2019-02-21"

keywords: authorizations, service to service access, access between services

subcollection: iam

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:tip: .tip}
{:note: .note}


# 授予服务之间的访问权
{: #serviceauth}

{{site.data.keyword.Bluemix_notm}} Identity and Access Management (IAM) 系统的许多功能都专注于按用户及其应用程序来管理和强制实施对 {{site.data.keyword.Bluemix_notm}} 资源的访问权。但是，有些情况可能需要为一个服务提供对另一个服务中用户资源的访问权。帐户中的所有用户都可以创建授权，但只有具有管理员角色的用户才能删除授权。您可以在**授权**页面上设置和查看您帐户中的授权。
{:shortdesc}

## 创建授权
{: #create-auth}

作为目标服务的用户，您只能授予自己拥有的访问级别。例如，如果您对要访问的服务仅具有查看者访问权，那么只能为授权分配查看者角色。

1. 在菜单栏中，单击**管理** &gt; **访问权 (IAM)**，然后选择**授权**。
2. 单击**创建**。
3. 选择授权的源和目标服务。源服务将被授予对所选目标服务的访问权。
4. 选择角色以向源服务分配访问目标服务的访问权。
5. 单击**授权**。

只有允许授予此类访问权的服务才会作为选项提供。
{: note}

## 除去授权
{: #remove-auth}

1. 在菜单栏中，单击**管理** &gt; **访问权 (IAM)**，然后选择**授权**。
2. 确定要从帐户中除去的授权所在的行。
3. 从**操作** ![“操作列表”图标](../icons/action-menu-icon.svg) 菜单中，选择**除去**。
5. 选择**除去**。
