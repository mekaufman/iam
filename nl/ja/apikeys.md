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

# API キーについて
{: #manapikey}

アプリケーション・プログラミング・インターフェース・キー (API キー) は、呼び出し側のアプリケーションまたはユーザーを識別するために API に渡される固有コードです。 API キーは、API の使用方法を追跡および制御する (例えば、API の悪用または不正利用を防止する) ために使用されます。 API キーは、多くの場合、認証のための固有 ID と秘密トークンの両方として機能し、通常はそのキーに関連付けられた ID に特定の一連のアクセス権限を持ちます。
{:shortdesc}

API キーを表示するには、**「管理」** > **「アクセス (IAM)」**と進み、**「ユーザー」**を選択します。 次に、ユーザーを選択して、「ユーザーの詳細」ページに含まれている「API キー」セクションにナビゲートします。

## {{site.data.keyword.cloud_notm}}API キー
{: #ibm-cloud-api-keys}

{{site.data.keyword.cloud}} API キーは、ユーザーの {{site.data.keyword.cloud_notm}} コンソールの「ユーザーの詳細」ページから作成され、ユーザーの ID と関連付けられます。 API キーを作成および削除できるのは、それが関連付けられているユーザーのみです。 {{site.data.keyword.cloud_notm}} API キーをコマンド・ライン・インターフェース (CLI) で使用したり、ログイン自動化の一部でユーザー ID として使用したりできます。 また、クラシック・インフラストラクチャー API にアクセスするために {{site.data.keyword.cloud_notm}} API キーを使用することもできます。 ユーザー ID に関連付けられた API キーの使用について詳しくは、[ユーザー API キーの管理](/docs/iam?topic=iam-userapikey#userapikey)を参照してください。

また、作成するサービス ID に関連付けられた API キーを使用することもできます。 サービス ID は、{{site.data.keyword.Bluemix_notm}} の内部または外部のアプリケーションを {{site.data.keyword.Bluemix_notm}} サービスに接続するために使用されます。 サービス ID に関連付けられた API キーの作成について詳しくは、[サービス ID の API キーの管理](/docs/iam?topic=iam-serviceidapikeys#serviceidapikeys)を参照してください。

## その他のタイプの API キー
{: #othertypes}

{{site.data.keyword.cloud_notm}} API キーに加えて、その他のいくつかのタイプの API キーを使用できる場合があります。

* クラシック・インフラストラクチャー API キー
* サービス固有の API キー

クラシック・インフラストラクチャー API キーは、クラシック・インフラストラクチャー・サービスの API を呼び出すために使用されます。 クラシック・インフラストラクチャー API キーは一度に 1 つしか作成できません。 「ユーザーの詳細」ページで、ユーザー用にクラシック・インフラストラクチャー API キーを作成できます。

クラシック・インフラストラクチャー API にアクセスするために {{site.data.keyword.cloud_notm}} API キーを使用することもできます。
{: tip}

{{site.data.keyword.Bluemix_notm}} 内のいくつかのサービスも、それらのサービスを操作するときにユーザーが使用する API キーを提供する場合があります。 例えば、ある Watson サービスのオファリング詳細をリソース・リストから表示しようとする場合、「サービス資格情報」ページでそのサービスにのみ固有の資格情報 (API キーと秘密を含む) を作成できます。
