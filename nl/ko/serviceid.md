---

copyright:

  years: 2017, 2019

lastupdated: "2019-05-10"

keywords: service ID, create service ID, lock service ID, service ID example

subcollection: iam

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:tip: .tip}
{:note: .note}

# 서비스 ID 작성 및 관련 작업 수행
{: #serviceids}

서비스 ID는 사용자 ID가 사용자를 식별하는 것과 유사한 방법으로 서비스 또는 애플리케이션을 식별합니다. 작성한 서비스 ID를 사용하여 {{site.data.keyword.Bluemix_notm}} 서비스에 대해 {{site.data.keyword.Bluemix_notm}} 액세스 외부에서 애플리케이션을 사용하도록 설정할 수 있습니다. 특정 서비스 사용을 위해 권한을 제한하거나 여러 서비스에 액세스하기 위해 권한을 결합하는 특정 액세스 정책을 서비스 ID에 지정할 수 있습니다. 서비스 ID는 특정 사용자에게 묶여 있지 않으므로, 사용자가 우연히 조직을 나가게 되어 계정에서 삭제되는 경우에도 서비스 ID는 남게 되어 애플리케이션 또는 서비스가 유지되고 실행됩니다.
{:shortdesc}

서비스 ID를 작성하는 경우 UI에서 식별하고 작업하기 쉬운 고유 이름 및 설명을 작성합니다. 서비스 ID를 작성하면, 애플리케이션에서 {{site.data.keyword.Bluemix_notm}} 서비스 인증에 사용할 수 있는 각 서비스 ID에 특정한 API 키를 작성할 수 있습니다. 애플리케이션에 {{site.data.keyword.Bluemix_notm}} 서비스 인증에 적합한 액세스 권한이 있는지 확인하기 위해, 작성하는 각 서비스 ID에 지정된 액세스 정책을 사용합니다.

서비스 ID와 연관된 액세스 정책은 해당 서비스 ID가 특정 서비스에 액세스하는 데 사용되는 경우 수행할 수 있는 특정 조치를 사용합니다. 단일 서비스 ID에는 여러 ID 및 액세스 사용 서비스와 심지어 단일 서비스의 여러 인스턴스에 액세스할 때 허용되는 액세스 레벨을 정의하는 다중 정책이 지정될 수 있습니다. 예를 들어, 각각 두 개의 서비스 인스턴스가 있는 두 개의 서비스가 있습니다. 예를 들어, 한 서비스의 사용 가능한 모든 인스턴스에 뷰어 역할을 지정하고 두 번째 서비스의 한 인스턴스에만 편집자 역할을 지정할 수 있습니다. 이와 같이 여러 서비스에 대한 액세스를 사용자 정의할 수 있지만 전체에 대한 인증에 단일 API 키를 사용할 수 있습니다.


## 서비스 ID 작성
{: #create_serviceid}

서비스 ID를 작성하려면 다음 단계를 완료하십시오.

1. **관리** &gt; **액세스(IAM)**로 이동하고 **서비스 ID**를 선택하십시오.
2. **작성**을 클릭하십시오.
3. 프로세스에 따라 서비스 ID의 이름과 설명을 작성하십시오.
4. **작성**을 클릭하십시오.

그런 다음, 서비스 ID의 행 위에 마우스 커서를 두어 나타나는 **조치** ![조치 목록 아이콘](../icons/action-menu-icon.svg) 메뉴를 통해 서비스 ID를 관리하십시오. 정책을 지정하고 API 키를 작성하여 시작할 수 있습니다. API 키를 사용한 작업에 대한 자세한 정보는 [서비스 ID API 키 관리](/docs/iam?topic=iam-serviceidapikeys#serviceidapikeys)를 참조하십시오.

## 서비스 ID 업데이트
{: #update_serviceid}

언제든 이름 및 설명을 변경하여 서비스 ID를 업데이트할 수 있습니다. 또한 필요에 따라 키를 삭제하고 새 API 키를 작성하거나 지정된 액세스 정책을 업데이트할 수도 있습니다. 서비스 ID의 행 위에 마우스 커서를 두어 나타나는 **조치** ![조치 목록 아이콘](../icons/action-menu-icon.svg) 메뉴를 통해 서비스 ID를 관리하십시오.

기존 서비스 ID를 변경하면(예: 지정된 정책 변경 또는 현재 사용 중인 API 키 삭제) 이 서비스 ID를 사용하는 애플리케이션에서 서비스가 중단될 수 있습니다.

## 서비스 ID 잠금
{: #lock_serviceid}

서비스 ID가 삭제되어 중단되거나 서비스 사용자를 방해하는 상황이 발생하는 것을 방지하기 위해 UI 또는 CLI를 사용하여 서비스 ID를 잠그는 옵션이 있어야 합니다. 서비스 ID를 잠그면 액세스 정책 변경, 삭제 또는 지정을 수행할 수 없습니다. 서비스 ID를 잠그는 기능 외에도 계정에 작성된 각 서비스 ID와 연관된 [개별 API 키 잠금](/docs/iam?topic=iam-serviceidapikeys#lockkey)을 수행할 수 있습니다.

잠긴 서비스 ID를 계정에서 삭제할 수 없고 액세스 정책을 업데이트할 수 없는 반면, 잠긴 서비스 ID가 추가된 액세스 그룹에서는 여전히 이 ID를 제거할 수 있습니다. 즉, 서비스 ID가 액세스 그룹에서 제거되면 액세스 그룹 내의 멤버십에 의해 ID에 지정된 모든 액세스가 제거됩니다.
{: note}

### 서비스 ID 잠금에 대한 사용자 액세스 제공
{: #access_lock_serviceid}

사용자가 서비스 ID 및 해당 서비스 ID와 연관된 API 키의 잠금 및 잠금 해제에 대한 액세스 권한을 갖도록 특정 액세스 정책이 지정되어야 합니다. 두 가지 유형의 액세스 정책에서 적절한 액세스(계정의 모든 서비스 ID에 대한 액세스 또는 계정의 특정 서비스 ID에 대한 액세스)를 부여할 수 있습니다.

계정 내의 모든 서비스 ID에 대한 액세스를 지정하려면 다음 세부사항을 사용하여 계정 관리 서비스에 대한 액세스 정책을 설정하십시오.

* 편집자 및 관리자 역할
* IAM ID 서비스

계정 내의 특정 서비스 ID에 대한 액세스를 지정하려면 다음 세부사항을 사용하여 계정 관리 서비스에 대한 액세스 정책을 설정하십시오.

* 편집자 및 관리자 역할
* IAM ID 서비스
* 리소스 유형 필드에 "serviceid" 지정
* 리소스 ID 필드에 서비스 ID의 ID 지정

특정 서비스 ID의 ID를 가져오려면 **관리** > **액세스(IAM)**로 이동하고 **서비스 ID**를 선택하십시오. 세부사항을 볼 서비스 ID를 선택한 후에 ID 값을 복사하십시오.
{: tip}

### UI에서 서비스 ID 잠금
{: #lock_serviceid_ui}

잠긴 서비스 ID는 ![잠김 아이콘](images/locked.svg "잠김") 아이콘으로 표시됩니다.

1. 메뉴 표시줄에서 **관리** &gt; **액세스(IAM)**를 클릭한 다음 **서비스 ID**를 선택하십시오.
2. 잠그려는 서비스 ID의 행을 식별하고 **조치** ![조치 목록 아이콘](../icons/action-menu-icon.svg) 메뉴에서 **서비스 ID 잠금**을 선택하십시오.

서비스 ID를 잠금 해제하려면 테이블에서 잠금 해제할 서비스 ID를 선택하고 **조치** ![조치 목록 아이콘](../icons/action-menu-icon.svg) 메뉴에서 **서비스 ID 잠금 해제**를 선택하십시오. 서비스 ID를 잠금 해제하려면 적절한 수준의 권한이 필요합니다.
{: tip}


### CLI를 사용하여 서비스 ID 잠금 및 잠금 해제
{: #lock_serviceid_cli}

서비스 ID를 잠그려면 다음 명령을 사용하십시오.

```
ibmcloud iam service-id-lock (NAME|UUID) [-f, --force]
```

명령 옵션:

<dl>
  <dt>NAME(필수)</dt>
  <dd>서비스의 이름(UUID와 배타적)</dd>
  <dt>UUID(필수)</dt>
  <dd>서비스의 UUID(NAME과 배타적)</dd>
  <dt>-f, --force</dt>
  <dd>확인 없이 잠금</dd>
</dl>

<strong>예제</strong>:

확인 없이 서비스 ID `sample-test` 잠금

```
ibmcloud iam service-id-lock sample-test -f
```

서비스 ID `ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976` 잠금

```
ibmcloud iam service-id-lock ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976
```

서비스 ID를 잠금 해제하려면 다음 명령을 사용하십시오.

 ```
ibmcloud iam service-id-unlock (NAME|UUID) [-f, --force]
```

명령 옵션:

<dl>
  <dt>NAME(필수)</dt>
  <dd>서비스의 이름(UUID와 배타적)</dd>
  <dt>UUID(필수)</dt>
  <dd>서비스의 UUID(NAME과 배타적)</dd>
  <dt>-f, --force</dt>
  <dd>확인 없이 잠금 해제</dd>
</dl>

<strong>예제</strong>:

확인 없이 서비스 ID `sample-test` 잠금 해제

```
ibmcloud iam service-id-unlock sample-test -f
```

서비스 ID `ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976` 잠금 해제

```
ibmcloud iam service-id-unlock ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976
```


## 서비스 ID 사용 방법의 예
{: #examples_serviceid}

다음은 {{site.data.keyword.objectstorageshort}} 및 Cloud SQL Query 서비스에 서비스 ID를 사용하는 방법에 대한 예입니다.

- {{site.data.keyword.objectstorageshort}} - [{{site.data.keyword.Bluemix_notm}} CLI 사용](/docs/services/cloud-object-storage?topic=cloud-object-storage-ic-use-the-ibm-cli#ic-hmac-credentials)
- Cloud SQL Query - [SQL Query REST API 사용법 ![외부 링크 아이콘](../icons/launch-glyph.svg)](https://www.youtube.com/embed/s6S4AdJItHk?rel=0){: new_window}을 참조하십시오.
