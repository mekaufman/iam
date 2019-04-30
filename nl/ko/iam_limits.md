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

# {{site.data.keyword.Bluemix_notm}} IAM 한계
{: #iam_limits}

다음 표에는 {{site.data.keyword.Bluemix_notm}} IAM(Identity and Access Management) 리소스에 대한 최대 한계가 나열되어 있습니다. 이러한 한계는 {{site.data.keyword.Bluemix_notm}} IAM 리소스를 작성할 수 있는 모든 사용자에게 적용되고, 한계를 초과하는 경우 예외를 수신하게 되며, 해당 한계를 초과하여 새 리소스를 작성할 수 없습니다.

|리소스 |최대 |
|----------|---------|
|계정당 액세스 그룹 |500 |
|사용자당 액세스 그룹 |50 |
|계정당 서비스 ID |2000 |
|ID당 API 키 |20 |
| 액세스 그룹별 동적 규칙 |5 |
{:caption="표 1. IAM 계정 한계" caption-side="top"}

계정 내에서 최적의 성능을 보장하기 위해 한 계정 내의 서비스 권한에 대해 최대 1,000개 정책 및 서비스가 권장됩니다.
{: tip}
