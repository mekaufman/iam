---

copyright:

  years: 2018, 2019

lastupdated: "2019-01-30"

keywords: IBM Cloud service APIs, IAM token, API key, authenticate with service API

subcollection: iam

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:tip: .tip}

# {{site.data.keyword.cloud_notm}} サービス API の呼び出し
{: #iamapikeysforservices}

API を介して {{site.data.keyword.Bluemix}} サービスを呼び出すには、サービスの API に資格情報を渡して、サービスのコンテキストでアクションを実行するためのユーザー ID およびアクセス権限を認証します。
{:shortdesc}

以下のいずれかの方法で呼び出し元を識別できます。

* {{site.data.keyword.Bluemix_notm}} API キーまたはサービス ID API キー
* {{site.data.keyword.Bluemix_notm}} Identity and Access Management (IAM) トークン

[{{site.data.keyword.Bluemix_notm}} API キー](/docs/iam?topic=iam-userapikey#userapikey)、[サービス ID API キー](/docs/iam?topic=iam-serviceidapikeys#serviceidapikeys)、および IAM トークンは、呼び出し元の ID を一意的に識別します。  呼び出し元 ID は、{{site.data.keyword.Bluemix_notm}} アカウント内に作成された、{{site.data.keyword.Bluemix_notm}} ユーザーまたはサービスの ID です。

API キーは、長い一連のランダムな文字または数字からなる資格情報です。 1 つの {{site.data.keyword.Bluemix_notm}} ID が複数の API キーを持つことができます。 これらの API キーはそれぞれ独立して管理できます。これは、ユーザーのサービスでのみ使用される API キーの場合、他のコンポーネントを中断せずにその API キーをユーザーが削除できることを意味します。

API キーを使用して、[{{site.data.keyword.Bluemix_notm}} コマンド・ライン・インターフェース (CLI) にログイン](/docs/cli/reference/ibmcloud?topic=cloud-cli-ibmcloud_login#ibmcloud_login)したり、[IAM トークンを生成](/docs/iam?topic=iam-iamtoken_from_apikey#iamtoken_from_apikey)したりできます。 実動での使用は推奨されませんが、API キーを {{site.data.keyword.Bluemix_notm}} サービスに送信することもできます。

## サービス API での認証のための {{site.data.keyword.Bluemix_notm}} API キーの引き渡し
{: #apikey_auth}

API クライアントは、ターゲット・サービスの API に {{site.data.keyword.Bluemix_notm}} API キーを直接渡すことができます。 これを行うには、基本許可 HTTP ヘッダーを使用して、ユーザー名として `apikey` キーワードを、パスワードとして {{site.data.keyword.Bluemix_notm}} API キーをターゲット・サービスに送信します。

ターゲット・サービス API は、{{site.data.keyword.Bluemix_notm}} IAM サービスを使用して、{{site.data.keyword.Bluemix_notm}} API キーをイントロスペクトする必要があります。 以下の図は、3 つの API 相互作用を示しています。 {{site.data.keyword.Bluemix_notm}} API キーは各ターゲット・サービスの API に渡されるため、各ターゲット・サービスが {{site.data.keyword.Bluemix_notm}} IAM を呼び出して {{site.data.keyword.Bluemix_notm}} API キー詳細を検索する必要があります。

![API キーを使用したサービス API での認証](images/APIkeyauth.svg "ターゲット・サービスに API キーを渡し、ターゲット・サービスは資格情報を検証するために API キーを IAM に渡す")

{{site.data.keyword.Bluemix_notm}} API キーの使用は便利であり、新しい API を見つけてプロトタイプを素早く試してみることが容易になります。 この方法では、{{site.data.keyword.Bluemix_notm}} API キーを読み取り可能な形式でターゲット・サービスの API に送信する必要があるため、API キーが不必要に漏えいされます。 さらに、ターゲット・サービスの API は必ず API キーをイントロスペクトする必要があるため、この方法は効率的ではなく、従って実動ワークロードには推奨されません。

API キーを使用してサービスの API で認証するには、以下の手順を実行します。

  1. まず、[{{site.data.keyword.Bluemix_notm}} API キーを作成](/docs/iam?topic=iam-userapikey#creating-an-api-key)します (まだ作成していない場合)。
  2. [RFC 7617](https://tools.ietf.org/html/rfc7617){: new_window} ![外部リンク・アイコン](../icons/launch-glyph.svg "外部リンク・アイコン") で定義されているように HTTP ヘッダー“Authorization”として {{site.data.keyword.Bluemix_notm}} API キーを送信します。 ユーザー名として `apikey` を、パスワードとして API キー値を使用します。

例えば、以下の手順では API キーが 0a1A2b3B4c5C6d7D8e9E であると想定しています。

  1.	ユーザー名 `apikey` と API キーをコロンで連結します: `apikey:0a1A2b3B4c5C6d7D8e9E`
  2.	このストリングを Base64 エンコード処理します: `base64("apikey:0a1A2b3B4c5C6d7D8e9E") => YXBpa2V5OjBhMUEyYjNCNGM1QzZkN0Q4ZTlF`
  3.	HTTP ヘッダー Authorization をスキーマ Basic を使用して設定します (例えば、`Authorization: Basic YXBpa2V5OjBhMUEyYjNCNGM1QzZkN0Q4ZTlF`)。 curl コマンドを使用するときは、パラメーター -u を使用してこれを渡すことができます。

    ```
    curl -u "apikey:<IBM Cloud API key value>"
    ```

  他のツールを使用する場合、これらの資格情報を異なる方法で指定しなければならない場合があります。
  {: tip}

## サービスの API での認証のための {{site.data.keyword.Bluemix_notm}} IAM トークンの引き渡し
{: #token_auth}

IAM アクセス・トークンを取得するには、まず、API クライアントは {{site.data.keyword.Bluemix_notm}} IAM API を呼び出して、そのトークンを認証および取得する必要があります。 {{site.data.keyword.Bluemix_notm}} サービス API クライアント向けの推奨される方法は、IAM API キーを使用して IAM アクセス・トークンを取得することです。 IAM アクセス・トークンは、認証方式として IAM アクセス・トークンを受け入れる {{site.data.keyword.Bluemix_notm}} サービスの複数回の呼び出しのために使用できます。 IAM アクセス・トークンは非対称鍵でデジタル署名されるため、{{site.data.keyword.Bluemix_notm}} サービスは、外部サービスを何も呼び出さずに IAM アクセス・トークンを検証できます。 これにより、API 呼び出しのパフォーマンスが大幅に向上します。

![サービス API でのアクセス・トークンを使用した認証](images/tokenauth.svg "API キーを使用して IAM からトークンを取得し、資格情報を検証するためにターゲット・サービスにアクセス・トークンを渡す")

アクセス・トークンを使用してサービスの API で認証するには、以下の手順を実行します。

  1. まず、[{{site.data.keyword.Bluemix_notm}} API キーを作成](/docs/iam?topic=iam-userapikey#creating-an-api-key)します (まだ作成していない場合)。
  2. API クライアントが行う次のステップは、『[API キーを使用した IAM トークンの取得](/docs/iam?topic=iam-iamtoken_from_apikey#iamtoken_from_apikey)』の説明に従って IAM アクセス・トークンを取得することです。
  3. 応答から、プロパティー `access_token` を抽出して IAM アクセス・トークンを取得します。 `expires_in` は、IAM アクセス・トークン `access_token` の有効期限が切れるまでの秒数を示します。 この相対値を使用するか、または、[UNIX 時刻](https://en.wikipedia.org/wiki/Unix_time){: new_window} ![外部リンク・アイコン](../icons/launch-glyph.svg "外部リンク・アイコン") に基づく絶対タイム・スタンプ `expiration` を使用します。
  4. [RFC 6750 セクション 2.1. Authorization Request Header Field](https://tools.ietf.org/html/rfc6750#page-5){: new_window} ![外部リンク・アイコン](../icons/launch-glyph.svg "外部リンク・アイコン") に記述されているように、IAM アクセス・トークンを送信します。

次の例を検討してください。

  1.	HTTP ヘッダー Authorization を使用します。
  2.	IAM アクセス・トークンの接頭部としてリテラル `Bearer: Bearer eyJhbGciOiJSUzI1Ng...` を付けます。
  3.	接頭部を付けた IAM アクセス・トークンを HTTP ヘッダーに追加します: `Authorization: Bearer eyJhbGciOiJSUzI1Ng...`。 curl コマンドを使用するときは、パラメーター -H を使用してこれを渡すことができます。

    ```
    curl -H "Authorization: Bearer eyJhbGciOiJSUzI1Ng..."
    ```

  同じ IAM アクセス・トークンを後続の IBM Cloud サービス API 呼び出しに使用することで、最高のパフォーマンスとスケーラビリティーを実現できます。
  {: tip}
