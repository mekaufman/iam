---

copyright:

  years: 2015, 2019
lastupdated: "2019-05-01"

keywords: service ID, service ID API key, lock service ID API key, delete service ID API key

subcollection: iam

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:tip: .tip}
{:note: .note}


# 서비스 ID API 키 관리
{: #serviceidapikeys}

서비스 ID는 {{site.data.keyword.Bluemix_notm}} 내부 및 외부 모두에서 호스팅되는 애플리케이션에 의한 {{site.data.keyword.Bluemix_notm}} 서비스 액세스가 가능하도록 작성되었습니다. API 키는 애플리케이션에서 사용되어 특정 서비스 ID로 인증하며 해당 서비스 ID와 연관된 액세스를 부여받습니다.
{:shortdesc}

서비스 ID를 작성하면 API 키 작성 및 서비스 정책 지정을 시작할 수 있습니다. 각 정책은 API 키가 서비스 인증에 사용될 때 허용되는 액세스 레벨을 지정합니다. 서비스 ID 작성 및 정책 지정에 대한 자세한 정보는 [서비스 ID 작성 및 관련 작업 수행](/docs/iam?topic=iam-serviceids#serviceids)을 참조하십시오. 서비스 ID API 키 관리에 사용되는 CLI 명령에 대한 세부사항은 [IAM 액세스, API 키, 서비스 ID 및 액세스 그룹 관리](/docs/cli/reference/ibmcloud?topic=cloud-cli-ibmcloud_commands_iam)를 참조하십시오.

서비스 ID와 연관된 각 API 키는 서비스 ID에 지정된 정책을 상속합니다. 예를 들어, 하나의 애플리케이션이 서비스 내에서 리소스를 볼 수 있게 하려면 정책이 뷰어 역할에 지정된 서비스 ID와 연관된 API 키를 사용해야 합니다. 그리고 다른 애플리케이션이 서비스 내에서 전체 액세스를 가질 수 있게 하려면 정책이 관리자 역할에 지정된 두 번째 서비스 ID와 연관된 API 키를 사용해야 합니다.

자세한 정보는 [서비스 ID 사용 방법에 대한 예제](/docs/iam?topic=iam-serviceids#examples_serviceid)를 참조하십시오.

## 서비스 ID의 API 키 작성
{: #create_service_key}

서비스 ID와 연관시킬 API 키를 작성하십시오.

1. **관리** &gt; **액세스(IAM)**로 이동하고 **서비스 ID**를 선택하십시오.
2. 서비스 ID가 아직 작성되지 않은 경우 서비스 ID를 작성하십시오.
3. **조치** ![조치 목록 아이콘](../icons/action-menu-icon.svg) 메뉴에서 **서비스 ID 관리**를 클릭하십시오.
4. **API 키**를 클릭하십시오.
5. **작성**을 클릭하십시오.
6. 이름 및 설명을 추가하여 API 키를 쉽게 식별하십시오.
7. **작성**을 클릭하십시오.
8. 보안 위치에 복사하거나 다운로드하여 API 키를 저장하십시오.

보안상의 이유로 인해 API 키는 작성 시에만 복사 또는 다운로드에 사용 가능합니다. API 키를 유실한 경우에는 새 API 키를 작성해야 합니다.
{: note}

CLI를 사용하여 서비스 ID에 대한 API 키를 작성하기 위해 [ibmcloud iam service-api-key-create](/docs/cli/reference/ibmcloud?topic=cloud-cli-ibmcloud_commands_iam#ibmcloud_iam_api_key_create) 명령을 사용할 수 있습니다.
```
ibmcloud iam service-api-key-create NAME SERVICE_ID [-d, --description DESCRIPTION] [--file FILE] [-f, --force]
```
{: codeblock}

## 서비스 ID의 API 키 업데이트
{: #update_service_key}

UI에서 키를 식별하는 데 사용되는 이름 또는 설명을 편집하여 API 키를 업데이트할 수 있습니다.

1. **관리** &gt; **액세스(IAM)**로 이동하고 **서비스 ID**를 선택하십시오.
2. **조치** ![조치 목록 아이콘](../icons/action-menu-icon.svg) 메뉴에서 **서비스 ID 관리**를 클릭하십시오.
3. **API 키**를 클릭하십시오.
4. **조치** ![조치 목록 아이콘](../icons/action-menu-icon.svg) 메뉴에서 **파일 이름 및 설명**을 클릭하십시오.

CLI를 사용하여 서비스 ID에 대한 API 키를 업데이트하기 위해 [ibmcloud iam service-api-key-update](/docs/cli/reference/ibmcloud?topic=cloud-cli-ibmcloud_commands_iam#ibmcloud_iam_api_key_update) 명령을 사용할 수 있습니다.
```
ibmcloud iam service-api-key-update NAME SERVICE_ID  [-n, --name NEW_sNAME] [-d, --description DESCRIPTION] [-v, --version VERSION] [-f, --force]
```
{: codeblock}

## 서비스 ID API 키 잠금
{: #lockkey}

서비스 ID의 ID를 나타내는 API 키에 대해 API 키를 잠그는 방법을 사용하여 삭제되지 않도록 방지할 수 있습니다. 잠긴 API 키는 UI에서 ![잠김 아이콘](images/locked.svg "잠김") 아이콘으로 표시됩니다.

1. 메뉴 표시줄에서 **관리** &gt; **액세스(IAM)**를 클릭하고 **서비스 ID**를 선택하십시오.
2. API 키를 선택할 서비스 ID의 행을 식별하고 서비스 ID의 이름을 선택하십시오.
3. **API 키**를 클릭하십시오.
4. 잠그려는 API 키의 행 위에 마우스 커서를 두어 나타나는 **조치** ![조치 목록 아이콘](../icons/action-menu-icon.svg) 메뉴를 클릭하여 옵션 목록을 여십시오.
5. **API 키 잠금**을 클릭하십시오.

액세스 정책을 업데이트, 삭제 또는 추가하거나 API 키를 제거하기 위해 언제든지 API 키를 잠금 해제할 수 있습니다.
{: tip}

### CLI를 사용하여 서비스 ID API 키 잠금 또는 잠금 해제
{: #lock_unlock_cli}

서비스 ID API 키를 잠그려면 다음 명령을 사용하십시오.

```
ibmcloud iam service-api-key-lock (APIKEY_NAME|APIKEY_UUID) (SERVICE_ID_NAME|SERVICE_ID_UUID) [-f, --force]
```

<strong>전제조건</strong>: 엔드포인트, 로그인, 대상

<strong>명령 옵션</strong>:
<dl>
  <dt>APIKEY_NAME(필수)</dt>
  <dd>API 키의 이름(APIKEY_UUID와 배타적)</dd>
  <dt>APIKEY_UUID(필수)</dt>
  <dd>API 키의 UUID(APIKEY_NAME과 배타적)</dd>
  <dt>SERVICE_ID_NAME(필수)</dt>
  <dd>서비스 ID의 이름(SERVICE_ID_UUID와 배타적)</dd>
  <dt>SERVICE_ID_UUID(필수)</dt>
  <dd>서비스 ID의 UUID(SERVICE_ID_NAME과 배타적)</dd>
  <dt>-f, --force</dt>
  <dd>확인 없이 잠금</dd>
</dl>

<strong>예제</strong>:

서비스 ID `sample-service`의 서비스 API 키 `sample-key` 잠금:

```
ibmcloud iam service-api-key-lock sample-key sample-service
```

서비스 ID API 키를 잠금 해제하려면 다음 명령을 사용하십시오.

```
ibmcloud iam service-api-key-unlock (APIKEY_NAME|APIKEY_UUID) (SERVICE_ID_NAME|SERVICE_ID_UUID) [-f, --force]
```


## 서비스 ID의 API 키 삭제
{: #delete_service_key}

서비스 ID와 연관된 API 키를 삭제할 수 있습니다. 하지만 애플리케이션이 현재 사용 중인 API 키를 삭제하면 서비스를 인증하는 해당 애플리케이션의 기능도 제거됩니다.

1. **관리** &gt; **액세스(IAM)**로 이동하고 **서비스 ID**를 선택하십시오.
2. 서비스 ID가 아직 작성되지 않은 경우 서비스 ID를 작성하십시오.
3. **조치** ![조치 목록 아이콘](../icons/action-menu-icon.svg) 메뉴에서 **서비스 ID 관리**를 클릭하십시오.
4. **API 키**를 클릭하십시오.
5. **조치** ![조치 목록 아이콘](../icons/action-menu-icon.svg) 메뉴에서 **삭제**를 클릭하십시오.

CLI를 사용하여 서비스 ID에 대한 API 키를 삭제하기 위해 [ibmcloud iam service-api-key-delete](/docs/cli/reference/ibmcloud?topic=cloud-cli-ibmcloud_commands_iam#ibmcloud_iam_api_key_delete) 명령을 사용할 수 있습니다.
```
ibmcloud iam service-api-key-delete NAME SERVICE_ID [-f, --force]
```
{: codeblock}
