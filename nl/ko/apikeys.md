---

copyright:

  years: 2015, 2019
lastupdated: "2019-01-30"

keywords: application programming interface key, API key, API, classic infrastructure API key, IBM Cloud API key

subcollection: iam

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:tip: .tip}

# API 키에 대한 이해
{: #manapikey}

API(Application Programming Interface) 키는 호출 애플리케이션 또는 사용자를 식별하도록 API에 전달되는 고유 코드입니다. API 키를 사용하여 API의 사용을 추적 및 제어할 수 있습니다. 예를 들어, 악의적 사용 또는 남용을 방지하는 데 이 API 키를 사용할 수 있습니다. API 키는 종종 인증을 위한 시크릿 토큰 및 고유 ID 모두의 역할을 하며, 일반적으로 이와 연관된 ID에 대한 액세스 세트를 보유합니다.
{:shortdesc}

API 키를 보려면 **관리** > **액세스(IAM)**로 이동하고 **사용자**를 선택하십시오. 그런 다음 사용자 세부사항 페이지에 포함된 API 키 섹션으로 이동할 사용자를 선택하십시오.

## {{site.data.keyword.cloud_notm}}API 키
{: #ibm-cloud-api-keys}

{{site.data.keyword.cloud}} API 키는 사용자를 위한 {{site.data.keyword.cloud_notm}} 콘솔의 사용자 세부사항 페이지에서 작성되며 사용자 ID와 연관됩니다. 연관된 API 키의 사용자만 이 키를 작성하고 삭제할 수 있습니다. 사용자 ID로 로그인하기 위해 자동화의 일부로 또는 명령행 인터페이스(CLI)에서 {{site.data.keyword.cloud_notm}} API 키를 사용할 수 있습니다. 또한 {{site.data.keyword.cloud_notm}} API 키를 사용하여 클래식 인프라 API에 액세스할 수 있습니다. 사용자 ID와 연관된 API 키 사용에 대한 자세한 정보는 [사용자 API 키 관리](/docs/iam?topic=iam-userapikey#userapikey)를 참조하십시오.

또한 작성하는 서비스 ID와 연관된 API 키를 사용할 수 있습니다. 서비스 ID를 사용하면 {{site.data.keyword.Bluemix_notm}}의 내부나 외부에 있는 애플리케이션을 {{site.data.keyword.Bluemix_notm}} 서비스에 연결할 수 있습니다. 서비스 ID와 연관된 API 키 작성에 대한 자세한 정보는 [서비스 ID API 키 관리](/docs/iam?topic=iam-serviceidapikeys#serviceidapikeys)를 참조하십시오.

## 다른 유형의 API 키
{: #othertypes}

{{site.data.keyword.cloud_notm}} API 키 외에 다음과 같은 몇 가지 다른 유형의 API 키를 사용할 수 있습니다.

* 클래식 인프라 API 키
* 서비스 특정 API 키

클래식 인프라 API 키는 클래식 인프라 서비스를 위한 API를 호출하는 데 사용됩니다. 한 번에 하나의 클래식 인프라 API 키만 작성할 수 있습니다. 사용자 세부사항 페이지에서 사용자를 위한 클래식 인프라 API 키를 작성할 수 있습니다.

또한 {{site.data.keyword.cloud_notm}} API 키는 클래식 인프라 API에 액세스하는 데 사용할 수 있습니다.
{: tip}

{{site.data.keyword.Bluemix_notm}}의 일부 서비스는 서비스에 대한 작업을 수행할 때 사용할 API 키를 제공할 수도 있습니다. 예를 들어, 리소스 목록에서 Watson 서비스의 오퍼링 세부사항을 보는 경우 서비스 인증 정보 페이지에서 해당 서비스에만 특정한 API 키 및 시크릿이 포함된 인증 정보를 작성할 수 있습니다.
