---

copyright:

  years: 2018, 2019

lastupdated: "2019-01-28"

keywords: specific IP addresses, IP addresses, restrict IP access, IP address access, allow IP access

subcollection: iam

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:tip: .tip}
{:note: .note}
{:important: .important}

# 允许用户使用特定 IP 地址
{: #ips}

缺省情况下，所有 IP 地址都可用于登录到 {{site.data.keyword.cloud}} 控制台并访问经典基础架构 API。您可以指定哪些 IP 地址具有访问权，这样就只能使用允许的指定地址，而其他所有地址都会受到限制。
{:shortdesc}

如果您具有受限 IP 地址，那么无法在 [https://cloud.ibm.com](https://cloud.ibm.com){: new_window} ![外部链接图标](../icons/launch-glyph.svg "外部链接图标") 上访问经典基础架构页面。您必须转至 [https://control.softlayer.com](https://control.softlayer.com){: new_window} ![外部链接图标](../icons/launch-glyph.svg "外部链接图标")。
{: important}

如果您具有以下分配的访问权，那么可以更新其他用户的受限 IP 地址：

  * 具有对用户管理服务的编辑者或更高角色的 IAM 策略。
  * 您在经典基础架构层次结构中是用户的祖代，并且分配有“管理用户”经典基础架构许可权。

如果您在“用户详细信息”页面上启用了“用户管理的登录设置”，那么您可以自行管理此设置。
{: tip}

要将用户限制为只使用特定 IP 地址，请完成以下步骤：

1. 在菜单栏中，单击**管理** &gt; **访问权 (IAM)**，然后选择**用户**。
2. 从列表中选择用户。
3. 在“用户详细信息”页面上，转至 **IP 地址限制**部分。
4. 对于**云平台**，输入 IP 地址。用户只能通过列出的 IP 地址登录到 {{site.data.keyword.Bluemix}}。
5. 对于**经典基础架构**，输入 IP 地址。用户只能通过列出的 IP 地址调用经典基础架构 API。

  要输入经典基础架构 IP 地址，用户必须已创建经典基础架构 API 密钥。
  {: note}
