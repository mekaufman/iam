---

copyright:

  years: 2015, 2017
lastupdated: "2017-12-07"

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}

# サービス ID の API キーの管理
{: #serviceidapikeys}

サービス ID は、{{site.data.keyword.Bluemix_notm}} の内部および外部の両方でホストされているアプリケーションによる {{site.data.keyword.Bluemix_notm}} サービスへのアクセスを可能にするために作成されます。 API キーは、特定のサービス ID としてアプリケーションを認証し、そのサービス ID に関連付けられたアクセス権限をアプリケーションに付与するために使用されます。

サービス ID を作成したら、API キーの作成とサービス・ポリシーの割り当てを開始できます。 各ポリシーは、サービスでの認証に API キーが使用された時に許可されるアクセス・レベルを指定します。 サービス ID の作成およびポリシーの割り当てについて詳しくは、[サービス ID の作成および管理](/docs/iam/serviceid.html#serviceids)を参照してください。 サービス ID の API キーの管理に使用される CLI コマンドの詳細については、[API キーとポリシーを管理するためのコマンド](/docs/cli/reference/bluemix_cli/bx_cli.html#bx_commands_iam)を参照してください。

サービス ID に関連付けられている各 API キーは、そのサービス ID に割り当てられているポリシーを継承します。 例えば、あるアプリケーションで、サービス内のリソースの表示のみを可能にしたい場合は、`Viewer` 役割が割り当てられたポリシーを持つサービス ID に関連した API キーを使用する必要があります。 そして、別のアプリケーションでは、サービス内でフルアクセスを持てるようにしたい場合は、`Administrator` 役割が割り当てられたポリシーを持つ 2 番目のサービス ID に関連付けられた API キーを使用する必要があります。

## サービス ID 用の API キーの作成

サービス ID に関連付ける API キーを作成します。

1. **「管理」** &gt; **「セキュリティー」** &gt; **「ID およびアクセス」** &gt; **「サービス ID」**に移動します。 
2. まだサービス ID を作成していない場合は、サービス ID を作成します。
3. **「アクション」**メニューから、**「サービス ID の管理」**オプションに進みます。
4. API キー・セクションで**「作成」**をクリックします。
5. API キーを容易に識別するための名前と説明を追加します。
6. **「作成」**をクリックします。
7. API キーを安全な場所にコピーまたはダウンロードして保存します。

**注**: 安全上の理由により、API キーをコピーまたはダウンロードできるのは作成時のみになります。 API キーが失われた場合は、新規 API キーを作成する必要があります。

## サービス ID 用の API キーの更新

API キーの更新は、UI で API キーを識別するために使用される名前または説明を編集することによって実行できます。

1. **「管理」** &gt; **「セキュリティー」** &gt; **「ID およびアクセス」** &gt; **「サービス ID」**に移動します。 
2. まだサービス ID を作成していない場合は、サービス ID を作成します。
3. **「アクション」**メニューから、**「サービス ID の管理」**オプションに進みます。
4. API キー・セクションの**「アクション」**メニューから、**「名前および説明の編集」**オプションに進みます。


## サービス ID 用の API キーの削除

サービス ID に関連付けられている API キーを削除することができます。 ただし、現在アプリケーションによって使用されている API キーを削除すると、サービスでそのアプリケーションの認証を行えなくなります。

1. **「管理」** &gt; **「セキュリティー」** &gt; **「ID およびアクセス」** &gt; **「サービス ID」**に移動します。 
2. まだサービス ID を作成していない場合は、サービス ID を作成します。
3. **「アクション」**メニューから、**「サービス ID の管理」**オプションに進みます。
4. API キー・セクションの**「アクション」**メニューから、**「キーの削除」**オプションに進みます。

