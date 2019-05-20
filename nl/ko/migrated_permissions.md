---

copyright:

  years: 2019

lastupdated: "2019-05-13"

keywords: migrated permissions, SoftLayer account permissions, migrated permission access group, migrated classic infrastructure permissions

subcollection: iam

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:important: .important}
{:new_window: target="_blank"}


# 마이그레이션된 SoftLayer 계정 권한 관리
{: #migrated_permissions}

액세스 그룹에는 이제 청구 정보를 보고 관리하며 지원 케이스를 처리할 수 있는 마이그레이션된 SoftLayer 계정 권한 세트가 포함됩니다. 이전에 이러한 권한이 지정된 계정의 사용자가 이제 마이그레이션된 각 권한 액세스 그룹에 지정됩니다. 따라서 IAM 액세스 그룹을 사용하여 권한을 직접 관리할 수 있습니다. {:shortdesc}

이러한 특수 액세스 그룹에는 SoftLayer 계정 권한의 원래 동작을 유지하기 위한 적절한 IAM 정책이 모두 포함됩니다. 예를 들어, 사용자가 지원 케이스에서 모든 사용자의 모든 업데이트를 계속 볼 수 있도록, 티켓팅 SoftLayer 계정 권한에 대한 마이그레이션된 권한 액세스 그룹에는 뷰어 역할이 지정된 사용자 관리 서비스에 대한 추가 IAM 정책이 포함됩니다. 자세한 정보는 [지원 케이스 작업을 위한 사용자 액세스 지정](/docs/get-support?topic=get-support-access#access)을 참조하십시오.

마이그레이션된 권한 액세스 그룹에서 이러한 마이그레이션된 클래식 인프라 권한을 추가하고 제거하여 IAM을 통해 직접 사용자의 해당 권한을 계속 관리할 수 있습니다. 이 액세스 그룹에 있는 정책은 해당 구성원의 액세스 작동을 유지하도록 잠겨 있습니다. 최근 IAM 사용자를 위한 사용 편의성을 유지하려면 이러한 액세스 그룹을 삭제하지 마십시오.

클래식 인프라 권한이 마이그레이션된 후에는 이러한 권한의 사용을 중지해야 합니다. 이제 IAM 액세스 그룹의 일부인, 모든 마이그레이션된 클래식 인프라 권한은 다음 표를 참조하십시오.
{: important}

| 마이그레이션된 권한 액세스 그룹 이름 | 허용된 조치 |
|----------|---------|
| 계정 요약 보기 | 계정 요약 페이지 및 송장과 결제 보기 |
| 규제 준수 보고서 가져오기 | 규제 준수 보고서 요청 |
| 회사 프로파일 편집 | 회사 프로파일 정보 편집 |
| 일시불 결제 | 사용자 계정에 대해 일시불 결제 |
| 결제 세부사항 업데이트 | 반복되는 월별 결제 정보 업데이트 |
| EU 케이스 제한 | 지원 케이스 데이터를 EU로 제한하는 EU 지원 옵션을 사용 또는 사용 안함으로 설정 |
| 케이스 추가 및 주문 보기 | 지원 케이스 작성 및 모든 주문 보기.  |
| 케이스 편집 | 지원 케이스 편집 |
| 케이스 검색 | 케이스 보기 권한도 지정된 경우 모든 지원 케이스 검색 |
| 케이스 보기 | 지원 케이스 모두 보기 |
{: caption="표 1. 사전 정의된 액세스 그룹" caption-side="top"}

