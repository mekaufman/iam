---

copyright:

  years: 2018, 2019

lastupdated: "2019-05-16"

keywords: event tracking, IAM events, monitoring

subcollection: iam

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:tip: .tip}
{:note: .note}
{:deprecated: .deprecated}

# IAM 事件跟踪
{: #tracking}

作为安全主管、审计员或管理者，您可以使用 {{site.data.keyword.at_full}} 服务来跟踪用户和应用程序如何与 {{site.data.keyword.Bluemix_notm}} Identity and Access Management (IAM) 交互。
{:shortdesc}

自 2019 年 5 月 9 日起，不推荐使用 {{site.data.keyword.cloudaccesstraillong}} 服务。您必须在帐户中创建 {{site.data.keyword.at_short}} 的实例，才能继续跟踪 IAM 事件。有关更多信息，请参阅[废弃 IBM Cloud Activity Tracker 服务](https://www.ibm.com/blogs/bluemix/2019/04/deprecating-ibm-cloud-activity-tracker/){: new_window} ![外部链接图标](../icons/launch-glyph.svg "外部链接图标")。
{: deprecated}

可以跟踪以下事件：

* 通过创建和删除组或添加和除去用户来管理访问组
* 创建、更新或删除服务标识
* 创建、更新或删除 API 密钥
* 创建、更新或删除访问策略
* 使用 API 密钥、授权代码、通行码、密码或与服务标识关联的 API 密钥登录到 {{site.data.keyword.Bluemix_notm}}

要开始监视用户的操作，请参阅 [{{site.data.keyword.at_short}}](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-getting-started#getting-started)。有关可以跟踪的每个事件区域的更多信息，请参阅 [IAM 事件](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-at_events_iam)。
