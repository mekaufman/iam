---

copyright:

  years: 2019

lastupdated: "2019-03-25"

keywords: public access, anonymous access

subcollection: iam

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:tip: .tip}
{:note: .note}

# 리소스에 대한 공용 액세스 사용
{: #public}

리소스에 대한 공용 액세스를 사용하면 모든 사용자 및 서비스 ID가 사용자의 계정 내의 특정 리소스에 액세스할 수 있습니다. 즉, 사용자 또는 서비스 ID가 {{site.data.keyword.cos_full_notm}} 버킷 내의 정보에 액세스하기 위해 {{site.data.keyword.Bluemix}}를 사용하여 인증할 필요가 없습니다. 특정 서비스만 서비스에 대한 특정 리소스 유형에 대한 공용 액세스를 지원할 수 있습니다. 따라서 이 기능을 지원하는 서비스에 대해서만 정책을 작성할 수 있습니다.
{:shortdesc}

리소스에 대한 공용 액세스를 사용하려면 계정 내에서 제공되는 **공용 액세스** 액세스 그룹을 사용해야 합니다. 이 액세스 그룹에는 기본적으로 모든 사용자 및 서비스 ID가 포함되어 있습니다. 그룹을 삭제하거나 그룹의 멤버십을 변경할 수는 없으나 그룹에 대한 액세스 정책을 추가, 편집 및 삭제할 수 있습니다.

## 공용 액세스 그룹에 대한 정책 작성
{: #public_policy}

다음 단계를 완료하여 공용 액세스 그룹에 정책을 지정하십시오. 다음 태스크에서는 `mybucket123`이라는 버킷에 공용 액세스를 지정하기 위해 예제로써 Cloud Object Storage 서비스를 사용합니다.

1. 메뉴 표시줄에서 **관리** &gt; **액세스(IAM)**를 클릭하고 **액세스 그룹**을 선택하십시오.
2. **공용 액세스** 그룹을 선택하십시오.
3. **액세스 지정**을 클릭하십시오.
4. 서비스 목록에서 **Cloud Object Storage**를 선택하십시오.
5. 리소스 유형으로 `bucket`을 입력하십시오.
6. 리소스 ID로 `mybucket123`을 입력하십시오.
7. **지정**을 클릭하십시오.
8. **예**를 클릭하여 리소스에 공용 액세스 정책을 지정함을 확인하고 **지정**을 클릭하십시오.
