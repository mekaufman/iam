---

copyright:

  years: 2019

lastupdated: "2019-07-02"

keywords: federated ID, enterprise SSO, SAML federation

subcollection: iam

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:tip: .tip}
{:new_window: target="_blank"}
{:deprecated: .deprecated}
    
# 非推奨の SAML 連携の管理
{: #saml-federation}

以前に SoftLayer カスタマー・ポータルで SAML ID プロバイダーを使用して連携をセットアップした場合、{{site.data.keyword.Bluemix}} コンソールの「ID プロバイダー」ページから、ID プロバイダー構成データを編集したり削除したりすることができます。
{: shortdesc}

このタイプの連携は非推奨です。この構成の削除は永続的であり、再びセットアップすることはできません。現在は IBMid との統合を利用することができます。詳しくは、[フェデレーテッド ID の登録](/docs/account?topic=account-signup#signup-federated)を参照してください。
{: deprecated}

SAML 構成データを編集するには、以下の手順を実行します。

1. **「管理」** > **「アクセス (IAM)」**と進み、**「ID プロバイダー」**を選択します。 
2. **「編集」**をクリックします。
3. 編集が必要なフィールド内の情報を変更します。
4. **「保存」**をクリックします。

非推奨の SAML 連携構成を削除するには、以下の手順を実行します。

1. **「管理」** > **「アクセス (IAM)」**と進み、**「ID プロバイダー」**を選択します。 
2. **「削除」**をクリックします。
3. 構成の削除が永続的であることを確認するオプションを選択します。このタイプの連携は非推奨であるため、再びセットアップすることはできません。
4. **「削除」**をクリックします。

