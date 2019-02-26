---

copyright:

  years: 2015, 2019
lastupdated: "2019-01-30"

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}

# ユーザーの API キーの管理
{: #userapikey}

フェデレーテッド・ユーザーまたは非フェデレーテッド・ユーザーは、API キーを作成し、CLI で使用したり、ID としてログインするための自動化の一部として使用したりすることができます。 キーのリスト、キーの作成、キーの更新、またはキーの削除を行うことにより、UI または CLI を使用して API キーを管理できます。 ユーザー ID に関連付けられた {{site.data.keyword.Bluemix_notm}} API キーを管理するには、**「管理」** &gt; **「アクセス (IAM)」**と進み、**「ユーザー」**を選択します。 次に、リストから自分の名前をクリックし、**「ユーザーの詳細」**オプションを選択して、API キーと説明および日付のリストを表示します。 次に、API キーを作成、編集、または削除できます。 そして、使用可能な CLI コマンドの全リストについては、[`ibmcloud iam api-keys`](/docs/cli/reference/ibmcloud?topic=cloud-cli-ibmcloud_commands_iam#ibmcloud_iam_api_keys) を参照してください。

[フェデレーテッド・ユーザー](/docs/account?topic=account-signup#signup)の場合、`IBMCLOUD_API_KEY` 環境変数を使用することにより、API キーを使用してログインできます。 ログインのための API キーの使用について詳しくは、[フェデレーテッド ID を使用したログイン](/docs/iam?topic=iam-federated_id#federated_id)を参照してください。
{:shortdesc}

## API キーの作成
{: #create_user_key}

{{site.data.keyword.Bluemix_notm}} ユーザーは、プログラムまたはスクリプトを使用可能にする際、パスワードをスクリプトに配布せずに、API キーを使用できます。 API キーを使用する利点は、ユーザーまたは組織が異なるプログラム用に複数の API キーを作成し、暗号漏えいが発生した場合、他の API キーやユーザーを妨害せずに、個別に API キーを削除できることです。 最大 20 個の API キーを作成できます。

UI でユーザー ID の API キーを作成するには、以下の手順を実行します。

1. **「管理」** &gt; **「アクセス (IAM)」**に移動して、**「ユーザー」**を選択します。 次に、リストから自分の名前をクリックし、**「ユーザーの詳細」**オプションを選択します。
2. **「{{site.data.keyword.Bluemix_notm}} API キーの作成」**をクリックします。
3. API キーの名前と説明を入力します。
4. **「作成」**をクリックします。
5. 次に、**「表示」**をクリックして API キーを表示し、後で使用するためにコピーして保存するか、または**「ダウンロード」**をクリックします。

安全上の理由により、API キーをコピーまたはダウンロードできるのは作成時のみになります。 API キーが失われた場合は、新規 API キーを作成する必要があります。
{: tip}

CLI を使用して API キーを作成するには、以下のコマンドを使用します。

1. コマンド・プロンプトに `ibmcloud iam api-key-create NAME [-d DESCRIPTION] [-f, --file FILE]` と入力し、名前と説明、およびキーを保存するためのファイルを指定します。 次の例を参照してください。

```
ibmcloud iam api-key-create MyKey -d "this is my API key" --file key_file
``` 


## API キーの更新
{: #update_user_key}

API キーの名前や説明を変更する場合は、UI または CLI で以下の手順を実行します。

API キーを編集するには、以下の手順を実行します。

1. **「管理」** &gt; **「アクセス (IAM)」**に移動して、**「ユーザー」**を選択します。 次に、リストから自分の名前をクリックし、**「ユーザーの詳細」**オプションを選択します。
2. 更新する API キーの行を識別し、**「アクション」** ![「アクションのリスト」アイコン](../icons/action-menu-icon.svg) メニューから**「編集」**を選択します。
3. API キーの情報を更新します。
4. **「適用」**をクリックします。

CLI を使用して API キーを編集するには、以下のコマンドを入力します。

1. コマンド・プロンプトに、キーの古い名前、新しい名前、および説明を指定して `ibmcloud iam api-key-update NAME [-n NAME] [-d DESCRIPTION]` と入力します。 例えば次のようにします。

```
ibmcloud iam api-key-update MyCurrentName -n MyNewName -d "the new description of my key"
```

## API キーのロック
{: #lock_user_key}

ユーザー ID を表すプラットフォーム API キーの場合、API キーをロックすることにより削除されないようにすることができます。 ロックされた API キーは、![ロック済みアイコン](images/locked.svg "ロック済み") アイコンで示されます。 API キーのロックとアンロックは、UI または CLI を使用して行うことができます。

### UI からの API キーのロックおよびアンロック
{: #lockui}

1. **「管理」** &gt; **「アクセス (IAM)」**に移動して、**「ユーザー」**を選択します。 次に、リストから自分の名前をクリックし、**「ユーザーの詳細」**オプションを選択します。
2. ロックする API キーの行を識別し、**「アクション」** ![「アクションのリスト」アイコン](../icons/action-menu-icon.svg) メニューから**「ロック」**を選択します。

API キーを更新したりアカウントから削除したりするために、API キーをいつでもアンロックできます。 アンロックする API キーを表から選択し、**「アクション」** ![「アクションのリスト」アイコン](../icons/action-menu-icon.svg) メニューから**「アンロック」**を選択します。
{: tip}

### CLI を使用した API キーのロックおよびアンロック
{: #lockcli}

API キーをロックするには、以下のコマンドを使用します。

```
ibmcloud iam api-key-lock (NAME|UUID) [-f, --force]
```

<strong>前提条件</strong>: エンドポイント、ログイン

<strong>コマンド・オプション</strong>:
<dl>
<dt>NAME (必須)</dt>
<dd>ロックする API キーの名前。UUID と同時に指定することはできません。</dd>
<dt>UUID (必須)</dt>
<dd>ロックする API キーの UUID。NAME と同時に指定することはできません。</dd>
<dt>-f, --force</dt>
<dd>確認なしでロックを強制します。</dd>
</dl>

<strong>例</strong>:

API キー `test-api-key` をロックします

```
ibmcloud iam api-key-lock test-api-key
```

API キーをアンロックするには、以下のコマンドを実行します。

```
ibmcloud iam api-key-unlock (NAME|UUID) [-f, --force]
```

<strong>前提条件</strong>: エンドポイント、ログイン

<strong>コマンド・オプション</strong>:
<dl>
<dt>NAME (必須)</dt>
<dd>アンロックする API キーの名前。UUID と同時に指定することはできません。</dd>
<dt>UUID (必須)</dt>
<dd>アンロックする API キーの UUID。NAME と同時に指定することはできません。</dd>
<dt>-f, --force</dt>
<dd>確認なしでアンロックを強制します。</dd>
</dl>

<strong>例</strong>:

API キー `test-api-key` をアンロックします

```
ibmcloud iam api-key-unlock test-api-key
```


## API キーの削除
{: #delete_user_key}

キーのローテーション戦略を使用している場合は、古いキーを削除し、新しいキーに置き換えることができます。

API キーを削除するには、以下の手順を実行します。 

1. **「管理」** &gt; **「アクセス (IAM)」**に移動して、**「ユーザー」**を選択します。 次に、リストから自分の名前をクリックし、**「ユーザーの詳細」**オプションを選択します。
2. 削除する API キーの行を識別し、**「アクション」** ![「アクションのリスト」アイコン](../icons/action-menu-icon.svg) メニューから**「削除」**を選択します。
3. 次に、**「削除」**をクリックして、削除を確認します。

CLI を使用して API キーを削除するには、以下の手順を実行します。
1. コマンド・プロンプトに、削除するキーの名前を指定して `ibmcloud iam api-key-delete NAME` と入力します。
