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

# サービス ID の作成と処理
{: #serviceids}

ユーザー ID がユーザーを識別するのと同様の方法で、サービス ID はサービスまたはアプリケーションを識別します。 作成したサービス ID は、{{site.data.keyword.Bluemix_notm}} の外部のアプリケーションが {{site.data.keyword.Bluemix_notm}} サービスにアクセスすることを可能にするために使用できます。 このサービス ID には、特定のサービスを使用するための許可を制限したり、さまざまなサービスにアクセスするための許可を結合したりする特定のアクセス・ポリシーを割り当てることができます。 サービス ID は特定のユーザーに結合されているわけではないため、ユーザーが組織を辞めてアカウントから削除されるようなことがあっても、サービス ID はそのまま残り、アプリケーションまたはサービスが確実に稼働し続けるようにします。
{:shortdesc}

サービス ID を作成する時は、UI での識別および作業が容易になるような固有の名前と説明を作成します。 サービス ID を作成したら、アプリケーションが {{site.data.keyword.Bluemix_notm}} サービスでの認証に使用できる、各サービス ID に固有の API キーを作成できます。 アプリケーションが {{site.data.keyword.Bluemix_notm}} サービスで認証を行うための適切なアクセス権限を持つようにするには、作成する各サービス ID に割り当てられるアクセス・ポリシーを使用します。

サービス ID に関連付けられたアクセス・ポリシーは、特定のサービスにアクセスするためにそのサービス ID が使用された時に実行できる特定のアクションを使用可能にします。 単一のサービス ID に、複数の ID およびアクセス対応サービス (および単一サービスのさまざまなインスタンス) にアクセスする時に許可されるアクセス・レベルを定義する複数のポリシーを割り当てることができます。 例えば、それぞれ 2 つのサービス・インスタンスを持つ 2 つのサービスがあるとします。 例えば、1 つのサービスのすべての使用可能インスタンスにビューアー役割を割り当て、2 番目のサービスの 1 つのインスタンスだけにエディター役割を割り当てるとします。 こうすると、複数のサービスへのアクセス権限をカスタマイズしながら、すべてに対する認証に単一の API キーを使用することができます。


## サービス ID の作成
{: #create_serviceid}

サービス ID を作成するには、以下の手順を実行します。

1. **「管理」** &gt; **「アクセス (IAM)」**に移動して、**「サービス ID」**を選択します。
2. **「作成」**をクリックします。
3. プロセスに従って、サービス ID の名前と説明を作成します。
4. **「作成」**をクリックします。

次に、サービス ID の行にカーソルを移動し、**「アクション」** ![「アクションのリスト」アイコン](../icons/action-menu-icon.svg) メニューを使用してサービス ID を管理します。 ポリシーの割り当てと API キーの作成から開始できます。 API キーの処理について詳しくは、『[サービス ID の API キーの管理](/docs/iam?topic=iam-serviceidapikeys#serviceidapikeys)』を参照してください。

## サービス ID の更新
{: #update_serviceid}

サービス ID は、名前と説明を変更することによっていつでも更新できます。 また、必要に応じて API キーを削除して新しく作成したり、割り当てられているアクセス・ポリシーを更新したりすることもできます。 サービス ID を管理するには、サービス ID の行にカーソルを移動し、**「アクション」** ![「アクションのリスト」アイコン](../icons/action-menu-icon.svg) メニューを使用します。

割り当てられているポリシーを変更したり、現在使用されている API キーを削除したりするなど、既存のサービス ID に対して変更を行うと、そのサービス ID を使用しているアプリケーションでサービスの中断が発生する可能性があります。

## サービス ID のロック
{: #lock_serviceid}

サービス ID の削除が原因でサービスのユーザーに中断や停止が発生する状態を避けるために、UI または CLI を使用してサービス ID をロックするオプションがあります。 サービス ID をロックすることにより、ポリシーの変更、削除、割り当てを防止することもできます。 サービス ID をロックできることに加え、アカウント内に作成する各サービス ID に関連付けられている[個々の API キーをロック](/docs/iam?topic=iam-serviceidapikeys#lockkey)できます。

ロックされたサービス ID をアカウントから削除することはできず、アクセス・ポリシーを更新することもできませんが、ロックされたサービス ID をそれらが追加されたアクセス・グループから削除することはできます。 つまり、アクセス・グループ内のメンバーシップによって ID に割り当てられているアクセス権限はいずれも、サービス ID がアクセス・グループから削除されたときに削除されます。
{: note}

### サービス ID をロックするためのユーザー・アクセス権限の提供
{: #access_lock_serviceid}

サービス ID およびサービス ID に関連付けられている API キーをロックおよびアンロックするためのアクセス権限をユーザーが持つためには、特定のアクセス・ポリシーが割り当てられている必要があります。 アカウント内のすべてのサービス ID へのアクセス権限、またはアカウント内の特定のサービス ID へのアクセス権限という 2 つのタイプのアクセス・ポリシーで、適切なアクセス権限を付与できます。

アカウント内のすべてのサービス ID へのアクセス権限を割り当てるには、以下の詳細を使用してアカウント管理サービスのアクセス・ポリシーを設定します。

* エディターまたは管理者の役割
* IAM Identity サービス

アカウント内の特定のサービス ID へのアクセス権限を割り当てるには、以下の詳細を使用してアカウント管理サービスのアクセス・ポリシーを設定します。

* エディターまたは管理者の役割
* IAM Identity サービス
* 「リソース・タイプ」フィールドに「serviceid」を指定する
* 「リソース ID」フィールドにサービス ID の識別子を指定する

特定のサービス ID の識別子を取得するには、**「管理」** > **「アクセス (IAM)」**と進み、**「サービス ID」**を選択します。 詳細を表示するサービス ID を選択し、ID の値をコピーします。
{: tip}

### UI からのサービス ID のロック
{: #lock_serviceid_ui}

ロックされたサービス ID は、![ロック済みアイコン](images/locked.svg "ロック済み") アイコンで示されます。

1. メニュー・バーから、**「管理」** &gt; **「アクセス (IAM)」**をクリックしてから、**「サービス ID」**を選択します。
2. ロックするサービス ID の行を特定し、**「アクション」**メニューから**「サービス ID のロック」** ![「アクションのリスト」アイコン](../icons/action-menu-icon.svg) を選択します。

サービス ID をアンロックするには、アンロックするサービス ID を表から選択し、**「アクション」**メニューから**「サービス ID のロック解除」** ![「アクションのリスト」アイコン](../icons/action-menu-icon.svg) を選択します。 サービス ID をアンロックするには、適切なレベルのアクセス権限を持っている必要があります。
{: tip}


### CLI を使用したサービス ID のロックおよびアンロック
{: #lock_serviceid_cli}

サービス ID をロックするには、以下のコマンドを使用します。

```
ibmcloud iam service-id-lock (NAME|UUID) [-f, --force]
```

コマンド・オプション:

<dl>
  <dt>NAME (必須)</dt>
  <dd>サービスの名前。UUID と同時に指定することはできません。</dd>
  <dt>UUID (必須)</dt>
  <dd>サービスの UUID。NAME と同時に指定することはできません。</dd>
  <dt>-f, --force</dt>
  <dd>確認を求めずにロックします</dd>
</dl>

<strong>例</strong>:

確認を求めずにサービス ID `sample-test` をロックします

```
ibmcloud iam service-id-lock sample-test -f
```

サービス ID `ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976` をロックします

```
ibmcloud iam service-id-lock ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976
```

サービス ID をアンロックするには、以下のコマンドを使用します。

 ```
ibmcloud iam service-id-unlock (NAME|UUID) [-f, --force]
```

コマンド・オプション:

<dl>
  <dt>NAME (必須)</dt>
  <dd>サービスの名前。UUID と同時に指定することはできません。</dd>
  <dt>UUID (必須)</dt>
  <dd>サービスの UUID。NAME と同時に指定することはできません。</dd>
  <dt>-f, --force</dt>
  <dd>確認を求めずにアンロックします</dd>
</dl>

<strong>例</strong>:

確認を求めずにサービス ID「sample-test」をアンロックします

```
ibmcloud iam service-id-unlock sample-test -f
```

サービス ID「ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976」をアンロックします

```
ibmcloud iam service-id-unlock ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976
```


## サービス ID の使用法の例
{: #examples_serviceid}

以下に、{{site.data.keyword.objectstorageshort}} サービスと Cloud SQL Query サービスでのサービス ID の使用方法の例を示します。

- {{site.data.keyword.objectstorageshort}} - [{{site.data.keyword.Bluemix_notm}} CLI の使用](/docs/services/cloud-object-storage?topic=cloud-object-storage-ic-use-the-ibm-cli#ic-hmac-credentials)
- Cloud SQL Query - [How to use the SQL Query REST API ![外部リンク・アイコン](../icons/launch-glyph.svg)](https://www.youtube.com/embed/s6S4AdJItHk?rel=0){: new_window}。
