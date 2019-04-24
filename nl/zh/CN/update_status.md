---

copyright:
  years: 2018, 2019
lastupdated: "2019-01-28"

keywords: user state, user status, change user status, update user status

subcollection: iam

---


{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:codeblock: .codeblock}
{:screen: .screen}
{:tip: .tip}
{:note: .note}

# 更新用户的状态
{: #status}

用户的已分配状态取决于用户是否已接受加入帐户的邀请，是否为仅使用 VPN 的用户，或者用户管理员是否将该用户设置为已禁用经典基础架构用户。
{:shortdesc}

如果您具有以下访问权，那么可以更新其他用户的状态：

  * 具有对用户管理服务的编辑者或更高角色的 IAM 策略。
  * 您在经典基础架构层次结构中是用户的祖代，并且分配有“管理用户”经典基础架构许可权。

有关用户状态类型的更多信息，请参阅[用户状态](/docs/iam?topic=iam-user_status#user_status)。

## 用于更改用户状态的选项
{: #status_options}

您可以从以下选项中进行选择，以更新用户的状态：

<dl>
<dt>活动</dt>
<dd>用户根据分配的访问策略和经典基础架构许可权，具有对 {{site.data.keyword.cloud_notm}} 控制台的完全访问权。</dd>
<dt>已禁用经典基础架构</dt>
<dd>用户无法再访问经典基础架构资源，但可以继续登录到控制台并访问平台资源。</dd>
<dt>仅使用 VPN</dt>
<dd>用户无法登录到控制台，但有权通过直接登录到设备来访问您为经典基础架构分配的任何设备和 VPN 子网。</dd>
</dl>

将用户从“仅使用 VPN”状态更新为“活动”状态时，该用户必须知道密码才能登录到控制台。在大多数情况下，这是 SoftLayer 标识密码，可能需要重置才能使用。在极少数情况下用户已具有 IBM 标识，这些用户必须使用 IBM 标识和密码登录。
{: note}

## 更新用户的状态
{: #update_user_status}

要更改用户的状态，请完成以下步骤：

1. 在菜单栏中，单击**管理** &gt; **访问权 (IAM)**，然后选择**用户**。
2. 从列表中选择用户。
3. 在“用户详细信息”页面中，从**用户状态**菜单中选择选项。  
4. 单击**应用**。
