---

copyright:

  years: 2018, 2019
lastupdated: "2019-01-30"

keywords: access groups, access group, create group, assign access to group

subcollection: iam

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:tip: .tip}
{:note: .note}


# アクセス・グループのセットアップ
{: #groups}

ユーザーおよびサービス ID の集合を単一のエンティティーに編成して、アクセス権限を簡単に割り当てられるようにするため、アクセス・グループを作成できます。 個々のユーザーまたはサービス ID ごとに同じアクセス権限を複数回割り当てるのではなく、単一のポリシーをグループに割り当てることができます。
{:shortdesc}

新規アクセス・グループを管理または作成するには、アカウント所有者であるか、アカウント内の IAM アクセス・グループ・サービスの管理者またはエディターであるか、すべてのアカウント管理サービスの、割り当てられた管理者またはエディターである必要があります。 さらに、リソースがアクセス・グループ ID であるアクセス・ポリシーを作成することにより、個々のグループを管理するためのアクセス権限を管理者またはエディターに割り当てることができます。 IAM アクセス・グループ・サービスのアクセス・ポリシーおよび役割について詳しくは、[IAM アクセス](/docs/iam?topic=iam-userroles#userroles)を参照してください。

アクセス権限の割り当てと管理をさらに簡単にするには、ユーザーのグループがアクセスできるリソースのセットを編成するように、リソース・グループをセットアップします。 リソース・グループがセットアップされたら、アカウント内の個々のサービス・インスタンス用にアクセス・ポリシーを作成するのではなく、そのグループ内のすべてのリソースに対するアクセス権限を付与するポリシーを割り当てることができます。
{: tip}

## アクセス・グループの作成
{: #create_ag}

アクセス・グループを作成するには、以下のステップを実行します。

1. メニュー・バーから、**「管理」** &gt; **「アクセス (IAM)」**をクリックして、**「アクセス・グループ」**を選択します。
2. **「作成」**をクリックします。
3. グループの名前と説明 (オプション) を入力して**「作成」**をクリックします。

次に、ユーザーまたはサービス ID を追加することでグループのセットアップに進みます。

1. 追加先のグループの名前を選択します。
2. **「ユーザー」**タブで**「ユーザーの追加」**をクリックします。
3. 追加するユーザーをリストから選択して、**「グループに追加 (Add to group)」**をクリックします。
4. サービス ID をグループに追加するには、**「サービス ID」**タブをクリックして、**「サービス ID の追加 (Add service ID)」**をクリックします。
5. 追加する ID をリストから選択して、**「グループに追加 (Add to group)」**をクリックします。

**「グループの削除 (Remove group)」**オプションを選択してグループを削除することができます。 グループをアカウントから削除すると、すべてのユーザーとサービス ID がグループから削除され、グループに割り当てられたすべてのアクセス権限が削除されます。
{: note}

CLI を使用してアクセス・グループを作成するには、[ibmcloud iam access-group-create](/docs/cli/reference/ibmcloud?topic=cloud-cli-ibmcloud_commands_iam#ibmcloud_iam_access_group_create) コマンドを使用します。
```
ibmcloud iam access-group-create GROUP_NAME [-d, --description DESCRIPTION]
```
{: codeblock}


## グループへのアクセス権限の割り当て
{: #access_ag}

ユーザーとサービス ID が含まれるグループをセットアップした後で、共通するアクセス・ポリシーをそのグループに割り当てることができます。 グループ用に設定するポリシーは、そのグループ内のすべてのエンティティーに適用されることを覚えておいてください。

1. メニュー・バーから、**「管理」** &gt; **「アクセス (IAM)」**をクリックして、**「アクセス・グループ」**を選択します。
2. アクセス権限を割り当てる先のグループの名前を選択します。
3. **「アクセス・ポリシー」**をクリックします。
4. **「アクセス権限の割り当て (Assign access)」**をクリックします。
5. リソース・グループ内のリソース別にアクセス権限を割り当てるのか、アカウント内で使用可能な個々のリソース別にアクセス権限を割り当てるのか、またはアカウント管理サービス別にアクセス権限を割り当てるのかを選択します。

CLI を使用してアクセス・グループ・ポリシーを作成するには、[ibmcloud iam access-group-policy-create](/docs/cli/reference/ibmcloud?topic=cloud-cli-ibmcloud_commands_iam#ibmcloud_iam_access_group_policy_create) コマンドを使用します。

```
ibmcloud iam access-group-policy-create GROUP_NAME {-f, --file @JSON_FILE | --roles ROLE_NAME1,ROLE_NAME2... [--service-name SERVICE_NAME] [--service-instance SERVICE_INSTANCE] [--region REGION] [--resource-type RESOURCE_TYPE] [--resource RESOURCE] [--resource-group-name RESOURCE_GROUP_NAME] [--resource-group-id RESOURCE_GROUP_ID]}
```
{: codeblock}
