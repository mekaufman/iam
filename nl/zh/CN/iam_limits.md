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

下表列出了 {{site.data.keyword.Bluemix_notm}} Identity and Access Management (IAM) 资源的最大限制。这些限制适用于可以创建 {{site.data.keyword.Bluemix_notm}} IAM 资源的任何用户。如果超过限制，您将收到异常，并且无法创建超过该限制的任何新资源。
{:shortdesc}

|资源|最大值|
|----------|---------|
|每个帐户的访问组数|500|
|每个用户的访问组数|50|
|每个帐户的服务标识数|2000|
|每个身份的 API 密钥数|20|
|每个访问组的动态规则数|5|
{:caption="表 1. IAM 帐户限制" caption-side="top"}

为了确保帐户内的最佳性能，建议一个帐户内最多包含 1,000 个策略和服务到服务授权。
{: tip}
