---

copyright:

  years: 2015，2019

lastupdated: "2019-03-27"

keywords: federated ID, enterprise SSO, single sign-on ID, API key login, one-time passcode login

subcollection: iam

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:tip: .tip}
{:new_window: target="_blank"}

# フェデレーテッド ID を使用したログイン
{: #federated_id}

会社または企業のシングル・サインオン ID を使用するフェデレーテッド・ユーザーは、ワンタイム・パスコードまたは API 鍵を使用してコマンド・ライン・インターフェース (CLI) から {{site.data.keyword.Bluemix}} にログインすることができます。
{: shortdesc}

## ワンタイム・パスコードの使用
{: #onetime_passcode}

ワンタイム・パスコード・オプションを使用してフェデレーテッド ID でログインする場合、シングルサインオン (SSO) パラメーターを指定してワンタイム・パスコードを取得し、それをログイン時に入力します。

ワンタイム・パスコードは {{site.data.keyword.Bluemix_notm}} コンソールからコードを取得するため、自動化スクリプトでのフェデレーテッド ID の使用は失敗します。 自動化スクリプトでは API キー・オプションを使用して問題を回避します。
{: tip}

### {{site.data.keyword.Bluemix_notm}} CLIから
{: #login_cli}
1. `ibmcloud login` コマンドに `--sso` オプションを指定します。
2. プロンプトの URL にアクセスしてワンタイム・パスコードを取得します。
3. 入力として CLI にパスコード値をコピー・アンド・ペーストします。

  ```
  ibmcloud login --sso
  API endpoint: https://cloud.ibm.com

  Get One Time Code from https://identity-2.us-south.iam.cloud.ibm.com/identity/passcode to proceed.
  Open the URL in the default browser? [Y/n]>
  One Time Code >
  Authenticating...
  OK

  ```

### Cloud Foundry CLI から
{: #login_cf_cli}

1. `cf login` コマンドに `--sso` オプションを指定します。
2. プロンプトの URL にアクセスしてワンタイム・パスコードを取得します。
3. 入力として CLI にパスコード値をコピー・アンド・ペーストします。

  ```
  cf login -a  https://api.us-south.cf.cloud.ibm.com --sso

  API endpoint: https://api.us-south.cf.cloud.ibm.com

  One Time Code (Get one at https://login.us-south.cf.cloud.ibm.com/UAALoginServerWAR/passcode)>
  Authenticating...
  OK

  ```

## API キーの使用
{: #api_key}

必要な API キーは、{{site.data.keyword.Bluemix_notm}} プラットフォームでの認証に使用される {{site.data.keyword.Bluemix_notm}} の API キーです。クラシック・インフラストラクチャー API キーまたは {{site.data.keyword.Bluemix_notm}} サービスの API キーではありません。

1. [`ibmcloud iam api-key-create` コマンド](/docs/cli/reference/ibmcloud?topic=cloud-cli-ibmcloud_commands_iam#ibmcloud_iam_api_key_create)を使用して API キーを作成します。 以下に示すように、コマンド・ウィンドウにキーを表示するのではなく API キー・ファイルを生成するには、`-f` オプションを使用します。

   ```
   ibmcloud iam api-key-create NAME [-d DESCRIPTION] [-f, --file FILE]

   ```

2. API キーを使用してログインします。

  API キーを {{site.data.keyword.Bluemix_notm}} CLI で使用するには、以下のいずれかの方法を使用できます。

    * 以下のように API キーを直接呼び出す。

      ```
      ibmcloud login --apikey <api_key_string>

      ```

    * 以下のようにキー・ファイルを使用して API キーを呼び出す。

      ```
      ibmcloud login --apikey @key_file_name

      ```

    * 環境変数を設定します。 さらに、ご使用のシステムにも環境変数を設定できます。 例えば、IBMCLOUD_API_KEY=api_key_string と指定します。ここで、`api_key_string` は、API キーのカスタム値です。 環境変数が設定された後は、CLI から単純に `ibmcloud login` を指定できます。

   Windows 10 PowerShell の場合は、キー・ファイル名を単一引用符で囲んで `'@key_file_name'` を使用します。
   {: tip}

  Cloud Foundry CLI を使用してログインするには、以下のように、ユーザー名として `apikey` を指定し、パスワードとして API キー・ストリングを指定します。

    ```
    cf login -a https://api.us-south.cf.cloud.ibm.com

    API endpoint: https://api.us-south.cf.cloud.ibm.com

    Email> apikey

    Password>
    Authenticating...
    OK

    ```
