---

copyright:
  years: 2018, 2019
lastupdated: "2019-03-08"

keywords: maximum limits, IBM Cloud IAM, limits, maximum policies

subcollection: iam

---


{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:codeblock: .codeblock}
{:screen: .screen}
{:tip: .tip}

# {{site.data.keyword.Bluemix_notm}} IAM 限制
{: #iam_limits}

下表列出 {{site.data.keyword.Bluemix_notm}} Identity and Access Management (IAM) 資源的上限。這些限制適用於可以建立 {{site.data.keyword.Bluemix_notm}} IAM 資源的任何使用者。如果超出限制，您會收到異常狀況，也不允許您建立超出該限制的任何新資源。
{:shortdesc}

|資源|上限|
|----------|---------|
|每個帳戶的存取群組| 500 |
|每個使用者的存取群組| 50 |
|每個帳戶的服務 ID|2000 |
|每個身分的 API 金鑰|20 |
|每個存取群組的動態規則| 5                |
{:caption="表 1. IAM 帳戶限制" caption-side="top"}

建議在一個帳戶內最多有 1,000 個原則和服務來維護授權，以確保您的帳戶能夠達到最佳效能。
{: tip}
