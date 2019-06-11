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

# IAM 事件追蹤
{: #tracking}

身為安全性管理者、審核員或管理員的您，可以使用 {{site.data.keyword.at_full}} 服務追蹤使用者和應用程式與 {{site.data.keyword.Bluemix_notm}} Identity and Access Management (IAM) 互動的情況。{:shortdesc}

自 2019 年 5 月 9 日開始，已淘汰 {{site.data.keyword.cloudaccesstraillong}} 服務。您必須在帳戶中建立 {{site.data.keyword.at_short}} 的實例，才能繼續追蹤 IAM 事件。如需相關資訊，請參閱[淘汰 IBM Cloud Activity Tracker 服務](https://www.ibm.com/blogs/bluemix/2019/04/deprecating-ibm-cloud-activity-tracker/){: new_window} ![外部鏈結圖示](../icons/launch-glyph.svg "外部鏈結圖示")。
{: deprecated}

您可以追蹤下列事件：

* 藉由建立及刪除群組或新增及移除使用者來管理存取群組
* 建立、更新或刪除服務 ID
* 建立、更新或刪除 API 金鑰
* 建立、更新或刪除存取原則
* 使用 API 金鑰、授權碼、通行碼、密碼或與服務 ID 相關聯的 API 金鑰來登入 {{site.data.keyword.Bluemix_notm}}

若要開始監視您使用者的動作，請參閱 [{{site.data.keyword.at_short}}](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-getting-started#getting-started)。如需您可以追蹤的每個事件區域的相關資訊，請參閱 [IAM 事件](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-at_events_iam)。
