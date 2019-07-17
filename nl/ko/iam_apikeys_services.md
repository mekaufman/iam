---

copyright:

  years: 2018, 2019

lastupdated: "2019-05-01"

keywords: IBM Cloud service APIs, IAM token, API key, authenticate with service API

subcollection: iam

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:tip: .tip}

# {{site.data.keyword.cloud_notm}} 서비스 API 호출
{: #iamapikeysforservices}

API를 통해 {{site.data.keyword.Bluemix}} 서비스를 호출하려면 서비스 API로 인증 정보를 전달하여 서비스 컨텍스트 내에서 조치를 수행하기 위한 사용자 ID와 액세스를 인증하십시오.
{:shortdesc}

다음 방법 중 하나로 호출자를 식별할 수 있습니다.

* {{site.data.keyword.Bluemix_notm}} API 키 또는 서비스 ID API 키
* {{site.data.keyword.Bluemix_notm}} IAM(Identity and Access Management) 토큰

[{{site.data.keyword.Bluemix_notm}} API 키](/docs/iam?topic=iam-userapikey#userapikey), [서비스 ID API 키](/docs/iam?topic=iam-serviceidapikeys#serviceidapikeys) 및 IAM 토큰이 호출자의 ID를 고유하게 식별합니다.  호출자 ID는 {{site.data.keyword.Bluemix_notm}} 계정에서 작성된 {{site.data.keyword.Bluemix_notm}} 사용자 또는 서비스 ID입니다.

API 키는 긴 일련의 임의 문자 또는 숫자로 구성된 인증 정보입니다. {{site.data.keyword.Bluemix_notm}} ID에 여러 API 키가 포함될 수 있습니다. 이러한 각 API 키는 개별적으로 관리될 수 있으며, 이는 이 API 키가 서비스에서만 사용되는 경우 다른 컴포넌트를 방해하지 않고 API 키를 삭제할 수 있음을 의미합니다.

API 키를 사용하여 [{{site.data.keyword.Bluemix_notm}} 명령행 인터페이스(CLI)에 로그인](/docs/cli/reference/ibmcloud?topic=cloud-cli-ibmcloud_cli#ibmcloud_login)하거나 [IAM 토큰을 생성](/docs/iam?topic=iam-iamtoken_from_apikey#iamtoken_from_apikey)할 수 있습니다. 이 API 키가 프로덕션 용도로 권장되지 않는 경우 API 키를 {{site.data.keyword.Bluemix_notm}} 서비스로 보낼 수 있습니다.

## {{site.data.keyword.Bluemix_notm}} API 키를 전달하여 서비스 API에서 인증
{: #apikey_auth}

API 클라이언트는 {{site.data.keyword.Bluemix_notm}} API 키를 직접 대상 서비스의 API에 전달할 수 있습니다. 이렇게 하려면 기본 권한 HTTP 헤더를 사용하여 `apikey` 키워드를 사용자 이름으로, {{site.data.keyword.Bluemix_notm}} API 키를 비밀번호로 대상 서비스에 보내십시오.

대상 서비스 API는 {{site.data.keyword.Bluemix_notm}} IAM 서비스를 사용하여 {{site.data.keyword.Bluemix_notm}} API 키를 조사해야 합니다. 다음 그래픽은 세 가지 API 상호작용을 보여줍니다. {{site.data.keyword.Bluemix_notm}} API 키는 모든 대상 서비스의 API로 전달되므로, 각 대상 서비스가 {{site.data.keyword.Bluemix_notm}} IAM을 호출하여 {{site.data.keyword.Bluemix_notm}} API 키 세부사항을 검색해야 합니다.

![API 키를 사용하여 서비스 API 인증](images/APIkeyauth.svg "API 키를 IAM으로 전달하는 대상 서비스로 API 키를 전달하여 인증 정보 유효성 검증"){: caption="Figure 1. Passing API keys to target services which then pass the API key to IAM to validate credentials" caption-side="bottom"}

{{site.data.keyword.Bluemix_notm}} API 키 사용은 편리하며 이를 통해 새 API를 쉽게 검색하고 신속하게 프로토타입을 사용해 볼 수 있습니다. 이 방법에서는 {{site.data.keyword.Bluemix_notm}} API 키를 읽기 가능한 형식으로 대상 서비스의 API에 보내야 하며, 이는 불필요하게 API 키를 손상시킵니다. 또한 대상 서비스의 API는 항상 API 키를 조사해야 하기 때문에 이 방법은 성능을 저하시키므로 프로덕션 워크로드에 권장되지 않습니다.

API 키를 사용하여 서비스의 API에서 인증하려면 다음 단계를 완료하십시오.

  1. 아직 없는 경우 먼저 [{{site.data.keyword.Bluemix_notm}} API 키를 작성](/docs/iam?topic=iam-userapikey#create_user_key)하십시오.
  2. HTTP 헤더 “Authorization”으로서 [RFC 7617](https://tools.ietf.org/html/rfc7617){: new_window} ![외부 링크 아이콘](../icons/launch-glyph.svg "외부 링크 아이콘")에 정의된 대로 {{site.data.keyword.Bluemix_notm}} API 키를 보내십시오. `apikey`를 사용자 이름으로, API 키 값을 비밀번호로 사용하십시오.

예로서 다음 단계에서는 API 키가 0a1A2b3B4c5C6d7D8e9E라고 가정합니다.

  1.	사용자 이름 `apikey`와 API 키를 콜론으로 구분하여 연결하십시오. `apikey:0a1A2b3B4c5C6d7D8e9E`
  2.	Base64가 문자열 인코딩: `base64("apikey:0a1A2b3B4c5C6d7D8e9E") => YXBpa2V5OjBhMUEyYjNCNGM1QzZkN0Q4ZTlF`
  3.	스키마가 Basic인 HTTP 헤더 권한을 설정하십시오(예: `Authorization: Basic YXBpa2V5OjBhMUEyYjNCNGM1QzZkN0Q4ZTlF`). curl 명령을 사용하는 경우 매개변수 -u와 함께 전달할 수 있습니다.

    ```
    curl -u "apikey:<IBM Cloud API key value>"
    ```

  다른 도구를 사용하는 경우 이러한 인증 정보를 다르게 지정해야 합니다.
  {: tip}

## {{site.data.keyword.Bluemix_notm}} IAM 토큰을 전달하여 서비스 API에서 인증
{: #token_auth}

IAM 액세스 토큰을 검색하려면 API 클라이언트가 먼저 {{site.data.keyword.Bluemix_notm}} IAM API를 호출하여 이 토큰을 인증하고 검색해야 합니다. {{site.data.keyword.Bluemix_notm}} 서비스 API 클라이언트에 대한 선호되는 방식은 IAM API 키를 사용하여 IAM 액세스 토큰을 가져오는 것입니다. IAM 액세스 토큰은 인증 방법으로 IAM 액세스 토큰을 허용하는 {{site.data.keyword.Bluemix_notm}} 서비스의 다중 호출에 사용할 수 있습니다. IAM 액세스 토큰이 비대칭 키를 사용하여 디지털로 서명되었으므로 {{site.data.keyword.Bluemix_notm}} 서비스는 외부 서비스를 호출하지 않고 IAM 액세스 토큰을 유효성 검증할 수 있습니다. 이는 API 호출 성능을 크게 향상시킵니다.

![액세스 토큰을 사용하여 서비스 API 인증](images/tokenauth.svg "API 키를 사용하여 IAM에서 토큰 검색 및 액세스 토큰을 대상 서비스로 전달하여 인증 정보 유효성 검증"){: caption="Figure 2. Retrieving a token from IAM by using an API key and passing the access token to target services to validate credentials" caption-side="bottom"}

액세스 토큰을 사용하여 서비스 API에서 인증하려면 다음 단계를 완료하십시오.

  1. 아직 없는 경우 먼저 [{{site.data.keyword.Bluemix_notm}} API 키를 작성](/docs/iam?topic=iam-userapikey#create_user_key)하십시오.
  2. [API 키에서 IAM 토큰 가져오기](/docs/iam?topic=iam-iamtoken_from_apikey#iamtoken_from_apikey)에 설명된 대로 API 클라이언트에 대한 다음 단계는 IAM 액세스 토큰 검색입니다.
  3. 응답에서 `access_token` 특성을 추출하여 IAM 액세스 토큰을 가져오십시오. `expires_in`은 IAM 액세스 토큰 `access_token`이 만료될 때까지의 시간(초)을 표시합니다. [UNIX 시간](https://en.wikipedia.org/wiki/Unix_time){: new_window} ![외부 링크 아이콘](../icons/launch-glyph.svg "외부 링크 아이콘")을 기반으로 한 절대 시간소인 `expiration` 또는 이 상대 값을 사용하십시오.
  4. [RFC 6750, 섹션 2.1. 권한 요청 헤더 필드](https://tools.ietf.org/html/rfc6750#page-5){: new_window} ![외부 링크 아이콘](../icons/launch-glyph.svg "외부 링크 아이콘")에 설명된 대로 IAM 액세스 토큰을 보내십시오.

다음 예를 검토하십시오.

  1.	HTTP 헤더 권한 사용
  2.	IAM 액세스 토큰에 리터럴 `Bearer: Bearer eyJhbGciOiJSUzI1Ng...`를 접두부로 사용
  3.	HTTP 헤더에 접두부인 IAM 액세스 토큰 추가: `Authorization: Bearer eyJhbGciOiJSUzI1Ng...`. curl 명령을 사용하는 경우 매개변수 -H와 함께 전달할 수 있습니다.

    ```
    curl -H "Authorization: Bearer eyJhbGciOiJSUzI1Ng..."
    ```

  후속 IBM Cloud 서비스 API 호출에 동일한 IAM 액세스 토큰을 사용하여 최고의 성능과 확장성을 달성하십시오.
  {: tip}
