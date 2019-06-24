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

# {{site.data.keyword.Bluemix_notm}} IAM の限度
{: #iam_limits}

以下の表に、{{site.data.keyword.Bluemix_notm}} Identity and Access Management (IAM) リソースの最大限度をリストします。 これらの限度は、{{site.data.keyword.Bluemix_notm}} IAM リソースを作成できるすべてのユーザーに適用されます。限度を超えると例外が出され、その限度を超えて新規リソースを作成することは許可されません。
{:shortdesc}

| リソース | 最大 |
|----------|---------|
| 　アカウント当たりのアクセス・グループ | 500 |
| ユーザー当たりのアクセス・グループ | 50 |
| アカウント当たりのサービス ID | 2000 |
| ID 当たりの API キー | 20 |
| アクセス・グループ当たりの動的ルール | 5 |
{:caption="表 1. IAM アカウントの限度" caption-side="top"}

アカウント内で最適のパフォーマンスを確保するため、1 つのアカウント内のポリシーおよびサービス間許可は、最大 1,000 個が推奨されます。
{: tip}
