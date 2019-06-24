---

copyright:

  years: 2018, 2019

lastupdated: "2019-01-30"

keywords: user list visibility, users page setting, user view access, limit access to users list, user list access

subcollection: iam

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}

# ユーザー表示権限の設定
{: #userlistview}

{{site.data.keyword.Bluemix}} アカウント所有者は、アカウント内のすべてのユーザーを表示することができ、ユーザーがアカウント内の他のユーザーをどの程度表示できるのかを定義できます。
{:shortdesc}

**「無制限ビュー」**オプションが選択されている場合、アカウント内のどのユーザーも、{{site.data.keyword.Bluemix_notm}} コンソールの「ユーザー」ページで他のユーザーを表示できます。 **「制限付きビュー」**オプションが選択されている場合、ユーザーはアカウント内の次のような特定のタイプのユーザーのみを表示できます。

* 自分が招待したユーザー
* Cloud Foundry 組織を自分と共有しているユーザー
* クラシック・インフラストラクチャー・ユーザー階層で自分の下位にいるユーザー (つまり、自分が招待したか、自分の下位にいる誰かが招待したユーザー)

デフォルトでは、アカウントには無制限ビューが設定されます。 この設定を更新するには、以下の手順を実行します。

1. メニュー・バーから、**「管理」** &gt; **「アクセス (IAM)」**をクリックして、**「設定」**を選択します。
2. **「ユーザー・リスト可視性」**設定に**「制限付きビュー」**を選択します。
