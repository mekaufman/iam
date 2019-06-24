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

# IAM 이벤트 추적
{: #tracking}

보안 담당자, 감사자 또는 관리자는 {{site.data.keyword.at_full}} 서비스를 사용하여 사용자 및 애플리케이션이 {{site.data.keyword.Bluemix_notm}} Identity and Access Management(IAM)와 어떻게 상호작용하는지 추적할 수 있습니다.
{:shortdesc}

2019년 5월 9일 현재 {{site.data.keyword.cloudaccesstraillong}} 서비스는 더 이상 사용되지 않습니다. IAM 이벤트 추적을 계속하려면 계정에 {{site.data.keyword.at_short}}의 인스턴스를 작성해야 합니다. 자세한 정보는 [IBM Cloud Activity Tracker 서비스 지원 중단](https://www.ibm.com/blogs/cloud-archive/2019/04/deprecating-ibm-cloud-activity-tracker/){: new_window} ![외부 링크 아이콘](../icons/launch-glyph.svg "외부 링크 아이콘")을 참조하십시오.
{: deprecated}

다음 이벤트를 추적할 수 있습니다.

* 그룹을 작성 및 삭제하거나 사용자를 추가 및 제거하여 액세스 그룹 관리
* 서비스 ID 작성, 업데이트 또는 삭제
* API 키 작성, 업데이트 또는 삭제
* 액세스 정책 작성, 업데이트 또는 삭제
* API 키, 권한 부여 코드, 패스코드, 비밀번호, 또는 서비스 ID와 연관된 API 키를 사용하여 {{site.data.keyword.Bluemix_notm}}에 로그인

사용자의 조치에 대한 모니터링을 시작하려면 [{{site.data.keyword.at_short}}](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-getting-started#getting-started)의 내용을 참조하십시오. 추적할 수 있는 각 이벤트 영역에 대한 자세한 정보는 [IAM 이벤트](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-at_events_iam)를 참조하십시오.
