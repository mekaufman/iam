---

copyright:

  years: 2015, 2019
lastupdated: "2019-01-30"

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:tip: .tip}
{:note: .note}


# サービス ID の API キーの管理
{: #serviceidapikeys}

サービス ID は、{{site.data.keyword.Bluemix_notm}} の内部および外部の両方でホストされているアプリケーションによる {{site.data.keyword.Bluemix_notm}} サービスへのアクセスを可能にするために作成されます。 API キーは、特定のサービス ID としてアプリケーションを認証し、そのサービス ID に関連付けられたアクセス権限をアプリケーションに付与するために使用されます。

サービス ID を作成したら、API キーの作成とサービス・ポリシーの割り当てを開始できます。 各ポリシーは、サービスでの認証に API キーが使用された時に許可されるアクセス・レベルを指定します。 サービス ID の作成およびポリシーの割り当てについて詳しくは、『[サービス ID の作成と処理](/docs/iam?topic=iam-serviceids#serviceids)』を参照してください。 サービス ID の API キーの管理に使用される CLI コマンドの詳細については、『[IAM アクセス権限、API キー、サービス ID、およびアクセス・グループの管理](/docs/cli/reference/ibmcloud?topic=cloud-cli-ibmcloud_commands_iam#ibmcloud_commands_iam)』を参照してください。

サービス ID に関連付けられている各 API キーは、そのサービス ID に割り当てられているポリシーを継承します。 例えば、あるアプリケーションで、サービス内のリソースの表示のみを可能にしたい場合は、ビューアー役割が割り当てられたポリシーを持つサービス ID に関連した API キーを使用する必要があります。 そして、別のアプリケーションでは、サービス内でフルアクセスを持てるようにしたい場合は、管理者役割が割り当てられたポリシーを持つ 2 番目のサービス ID に関連付けられた API キーを使用する必要があります。

詳しくは、[サービス ID の使用方法の例](/docs/iam?topic=iam-serviceids#examples_serviceid)を参照してください。

## サービス ID 用の API キーの作成
{: #create_service_key}

サービス ID に関連付ける API キーを作成します。

1. **「管理」** &gt; **「アクセス (IAM)」**に移動して、**「サービス ID」**を選択します。
2. まだサービス ID を作成していない場合は、サービス ID を作成します。
3. **「アクション」** ![「アクションのリスト」アイコン](../icons/action-menu-icon.svg) メニューから**「サービス ID の管理」**をクリックします。
4. **「API キー」**をクリックします。
5. **「作成」**をクリックします。
6. API キーを容易に識別するための名前と説明を追加します。
7. **「作成」**をクリックします。
8. API キーを安全な場所にコピーまたはダウンロードして保存します。

安全上の理由により、API キーをコピーまたはダウンロードできるのは作成時のみになります。 API キーが失われた場合は、新規 API キーを作成する必要があります。
{: note}

CLI を使用してサービス ID の API キーを作成するには、[ibmcloud iam service-api-key-create](/docs/cli/reference/ibmcloud?topic=cloud-cli-ibmcloud_iam_api_key_create#ibmcloud_iam_service_api_key_create) コマンドを使用します。
```
ibmcloud iam service-api-key-create NAME SERVICE_ID [-d, --description DESCRIPTION] [--file FILE] [-f, --force]
```
{: codeblock}

## サービス ID 用の API キーの更新
{: #update_service_key}

API キーの更新は、UI で API キーを識別するために使用される名前または説明を編集することによって実行できます。

1. **「管理」** &gt; **「アクセス (IAM)」**に移動して、**「サービス ID」**を選択します。
2. **「アクション」** ![「アクションのリスト」アイコン](../icons/action-menu-icon.svg) メニューから**「サービス ID の管理」**をクリックします。
3. **「API キー」**をクリックします。
4. **「アクション」** ![「アクションのリスト」アイコン](../icons/action-menu-icon.svg) メニューから**「名前および説明の編集」**をクリックします。

CLI を使用してサービス ID の API キーを更新するには、[ibmcloud iam service-api-key-update](/docs/cli/reference/ibmcloud?topic=cloud-cli-ibmcloud_iam_api_key_create#ibmcloud_iam_service_api_key_update) コマンドを使用します。
```
ibmcloud iam service-api-key-update NAME SERVICE_ID  [-n, --name NEW_sNAME] [-d, --description DESCRIPTION] [-v, --version VERSION] [-f, --force]
```
{: codeblock}

## サービス ID の API キーのロック
{: #lockkey}

サービス ID のアイデンティティーを表す API キーの場合、API キーをロックすることにより削除されないようにすることができます。 ロックされた API キーは、UI 上に ![ロック済みアイコン](images/locked.svg "ロック済み") アイコンで示されます。

1. メニュー・バーから、**「管理」** &gt; **「アクセス (IAM)」**をクリックして、**「サービス ID」**を選択します。
2. API キーの選択対象サービス ID の行を特定し、サービス ID の名前を選択します。
3. **「API キー」**をクリックします。
4. ロックする API キーの行の上にカーソルを移動し、**「アクション」** ![「アクションのリスト」アイコン](../icons/action-menu-icon.svg) メニューをクリックしてオプション・リストを開きます。
5. **「API キーのロック (Lock API key)」**をクリックします。

アクセス・ポリシーを更新、削除、または追加したり、API キーを削除したりするために、API キーはいつでもアンロックできます。
{: tip}

### CLI を使用したサービス ID の API キーのロックまたはアンロック
{: #lock_unlock_cli}

サービス ID の API キーをロックするには、以下のコマンドを使用します。

```
ibmcloud iam service-api-key-lock (APIKEY_NAME|APIKEY_UUID) (SERVICE_ID_NAME|SERVICE_ID_UUID) [-f, --force]
```

<strong>前提条件</strong>: エンドポイント、ログイン、ターゲット

<strong>コマンド・オプション</strong>:
<dl>
  <dt>APIKEY_NAME (必須)</dt>
  <dd>API キーの名前。APIKEY_UUID と同時に指定することはできません。</dd>
  <dt>APIKEY_UUID (必須)</dt>
  <dd>API キーの UUID。APIKEY_NAME と同時に指定することはできません。</dd>
  <dt>SERVICE_ID_NAME (必須)</dt>
  <dd>サービス ID の名前。SERVICE_ID_UUID と同時に指定することはできません。</dd>
  <dt>SERVICE_ID_UUID (必須)</dt>
  <dd>サービス ID の UUID。SERVICE_ID_NAME と同時に指定することはできません。</dd>
  <dt>-f, --force</dt>
  <dd>確認を求めずにロックします</dd>
</dl>

<strong>例</strong>:

サービス ID `sample-service` のサービス API キー `sample-key` をロックします

```
ibmcloud iam service-api-key-lock sample-key sample-service
```

サービス ID の API キーをアンロックするには、以下のコマンドを使用します。

```
ibmcloud iam service-api-key-unlock (APIKEY_NAME|APIKEY_UUID) (SERVICE_ID_NAME|SERVICE_ID_UUID) [-f, --force]
```


## サービス ID 用の API キーの削除
{: #delete_service_key}

サービス ID に関連付けられている API キーを削除することができます。 ただし、現在アプリケーションによって使用されている API キーを削除すると、サービスでそのアプリケーションの認証を行えなくなります。

1. **「管理」** &gt; **「アクセス (IAM)」**に移動して、**「サービス ID」**を選択します。
2. まだサービス ID を作成していない場合は、サービス ID を作成します。
3. **「アクション」** ![「アクションのリスト」アイコン](../icons/action-menu-icon.svg) メニューから**「サービス ID の管理」**をクリックします。
4. **「API キー」**をクリックします。
5. **「アクション」** ![「アクションのリスト」アイコン](../icons/action-menu-icon.svg) メニューから**「削除」**をクリックします。

CLI を使用してサービス ID の API キーを削除するには、[ibmcloud iam service-api-key-delete](/docs/cli/reference/ibmcloud?topic=cloud-cli-ibmcloud_iam_api_key_create#ibmcloud_iam_service_api_key_delete) コマンドを使用します。
```
ibmcloud iam service-api-key-delete NAME SERVICE_ID [-f, --force]
```
{: codeblock}
