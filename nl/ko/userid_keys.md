---

copyright:

  years: 2015, 2019
lastupdated: "2019-01-30"

keywords: API key, user API keys, IBM Cloud API keys, manage user keys, create API key

subcollection: iam

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}

# 사용자 API 키 관리
{: #userapikey}

연합 또는 비연합 사용자는 CLI에서 또는 자동화의 일부로 사용하여 사용자 ID로 로그인하기 위해 API 키를 작성할 수 있습니다. UI 또는 CLI를 사용하여 키 나열, 키 작성, 키 업데이트 또는 키 삭제를 수행하여 API 키를 관리할 수 있습니다. 사용자 ID와 연관된 {{site.data.keyword.Bluemix_notm}} API 키를 관리하려면 **관리** &gt; **액세스(IAM)**로 이동하고 **사용자**를 선택하십시오. 그런 다음 목록에서 이름을 클릭하고 **사용자 세부사항** 옵션을 선택하여 설명 및 날짜가 포함된 API 키 목록을 보십시오. 그런 다음 API 키를 작성, 편집 또는 삭제할 수 있습니다. 또한 사용 가능한 CLI 명령의 전체 목록은 [`ibmcloud iam api-keys`](/docs/cli/reference/ibmcloud?topic=cloud-cli-ibmcloud_commands_iam#ibmcloud_iam_api_keys)를 참조하십시오.

[연합 사용자](/docs/account?topic=account-signup#signup)는 `IBMCLOUD_API_KEY` 환경 변수를 사용하여 로그인하는 데 API 키를 사용할 수 있습니다. 로그인을 위한 API 키 사용에 대한 자세한 정보는 [연합 ID로 로그인](/docs/iam?topic=iam-federated_id#federated_id)을 참조하십시오.
{:shortdesc}

## API 키 작성
{: #create_user_key}

{{site.data.keyword.Bluemix_notm}} 사용자는 스크립트에 비밀번호를 제공하지 않고 API 키를 사용하여 프로그램 또는 스크립트를 사용할 수 있습니다. API 키를 사용하면 사용자나 조직이 다양한 프로그램에 대해 여러 API 키를 작성할 수 있으며, 문제가 발생할 경우 다른 API 또는 사용자에게 영향을 주지 않고 개별적으로 API 키를 삭제할 수 있습니다. 최대 20개의 API 키를 작성할 수 있습니다.

UI에서 사용자 ID의 API 키를 작성하려면 다음 단계를 완료하십시오.

1. **관리** &gt; **액세스(IAM)**로 이동하고 **사용자**를 선택하십시오. 그런 다음, 목록에서 이름을 클릭하고 **사용자 세부사항** 옵션을 선택하십시오.
2. **{{site.data.keyword.Bluemix_notm}} API 키 작성**을 클릭하십시오.
3. API 키의 이름과 설명을 입력하십시오.
4. **작성**을 클릭하십시오.
5. 그런 다음 **표시**를 클릭하여 나중에 복사하고 저장할 수 있도록 API 키를 표시하거나 **다운로드**를 클릭하십시오.

보안상의 이유로 인해 API 키는 작성 시에만 복사 또는 다운로드에 사용 가능합니다. API 키를 유실한 경우에는 새 API 키를 작성해야 합니다.
{: tip}

CLI를 사용하여 API 키를 작성하려면 다음 명령을 사용하십시오.

1. 명령 프롬프트에 `ibmcloud iam api-key-create NAME [-d DESCRIPTION] [-f, --file FILE]`을 입력하고 이름, 설명 및 키를 저장하기 위한 파일을 지정하십시오. 다음 예를 참조하십시오.

```
ibmcloud iam api-key-create MyKey -d "this is my API key" --file key_file
```


## API 키 업데이트
{: #update_user_key}

API 키의 설명 또는 이름을 변경하려는 경우, UI 또는 CLI에서 다음 단계를 완료하십시오.

API 키를 편집하려면 다음 단계를 완료하십시오.

1. **관리** &gt; **액세스(IAM)**로 이동하고 **사용자**를 선택하십시오. 그런 다음, 목록에서 이름을 클릭하고 **사용자 세부사항** 옵션을 선택하십시오.
2. 업데이트할 API 키의 행을 식별하고 **조치** ![조치 목록 아이콘](../icons/action-menu-icon.svg) 메뉴에서 **편집**을 선택하십시오.
3. API 키에 대한 정보를 업데이트하십시오.
4. **적용**을 클릭하십시오.

CLI를 사용하여 API 키를 편집하려면 다음 명령을 입력하십시오.

1. 명령 프롬프트에 `ibmcloud iam api-key-update NAME [-n NAME] [-d DESCRIPTION]`을 입력하여 키의 이전 이름, 새 이름 및 새 설명을 지정하십시오. 예를 들어, 다음과 같습니다.

```
ibmcloud iam api-key-update MyCurrentName -n MyNewName -d "the new description of my key"
```

## API 키 잠금
{: #lock_user_key}

사용자 ID를 나타내는 플랫폼 API 키에 대해 API 키를 잠그는 방법을 사용하여 삭제되지 않도록 방지할 수 있습니다. 잠긴 API 키는 ![잠김 아이콘](images/locked.svg "잠김") 아이콘으로 표시됩니다. UI 또는 CLI를 사용하여 API 키를 잠그거나 잠금 해제할 수 있습니다.

### UI에서 API 키 잠금 및 잠금 해제
{: #lockui}

1. **관리** &gt; **액세스(IAM)**로 이동하고 **사용자**를 선택하십시오. 그런 다음, 목록에서 이름을 클릭하고 **사용자 세부사항** 옵션을 선택하십시오.
2. 잠그려는 API 키의 행을 식별하고 **조치** ![조치 목록 아이콘](../icons/action-menu-icon.svg) 메뉴에서 **잠금**을 선택하십시오.

계정에서 API 키를 업데이트하거나 제거하기 위해 언제든 API 키를 잠금 해제할 수 있습니다. 테이블에서 잠금 해제할 API 키를 선택하고 **조치** ![조치 목록 아이콘](../icons/action-menu-icon.svg) 메뉴에서 **잠금 해제**를 선택하십시오.
{: tip}

### CLI를 사용하여 API 키 잠금 및 잠금 해제
{: #lockcli}

API 키를 잠그려면 다음 명령을 사용하십시오.

```
ibmcloud iam api-key-lock (NAME|UUID) [-f, --force]
```

<strong>전제조건</strong>: 엔드포인트, 로그인

<strong>명령 옵션</strong>:
<dl>
<dt>NAME(필수)</dt>
<dd>잠글 API 키의 이름(UUID와 배타적)</dd>
<dt>UUID(필수)</dt>
<dd>잠글 API 키의 UUID(NAME과 배타적)</dd>
<dt>-f, --force</dt>
<dd>확인 없이 강제로 잠급니다.</dd>
</dl>

<strong>예제</strong>:

API 키 `test-api-key` 잠금

```
ibmcloud iam api-key-lock test-api-key
```

API 키를 잠금 해제하려면 다음 명령을 실행하십시오.

```
ibmcloud iam api-key-unlock (NAME|UUID) [-f, --force]
```

<strong>전제조건</strong>: 엔드포인트, 로그인

<strong>명령 옵션</strong>:
<dl>
<dt>NAME(필수)</dt>
<dd>잠금 해제할 API 키의 이름(UUID와 배타적)</dd>
<dt>UUID(필수)</dt>
<dd>잠금 해제할 API 키의 UUID(NAME과 배타적)</dd>
<dt>-f, --force</dt>
<dd>확인 없이 강제로 잠금 해제합니다.</dd>
</dl>

<strong>예제</strong>:

API 키 `test-api-key` 잠금 해제

```
ibmcloud iam api-key-unlock test-api-key
```


## API 키 삭제
{: #delete_user_key}

키 회전 전략을 사용하는 경우, 이전 키를 삭제하고 새 키로 바꾸려고 할 수 있습니다.

API 키를 삭제하려면 다음 단계를 완료하십시오.

1. **관리** &gt; **액세스(IAM)**로 이동하고 **사용자**를 선택하십시오. 그런 다음, 목록에서 이름을 클릭하고 **사용자 세부사항** 옵션을 선택하십시오.
2. 삭제할 API 키의 행을 식별하고 **조치** ![조치 목록 아이콘](../icons/action-menu-icon.svg) 메뉴에서 **삭제**를 선택하십시오.
3. 그런 다음 **삭제**를 클릭하여 삭제를 확인하십시오.

CLI를 사용하여 API 키를 삭제하려면 다음을 수행하십시오.
1. 명령 프롬프트에 `ibmcloud iam api-key-delete NAME`을 입력하여 삭제할 키의 이름을 지정하십시오.
