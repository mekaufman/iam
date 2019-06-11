---

copyright:

  years: 2018, 2019

lastupdated: "2019-05-16"

keywords: event tracking, IAM events, monitoring

subcollection: iam

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:tip: .tip}
{:note: .note}
{:deprecated: .deprecated}

# IAM イベントのトラッキング
{: #tracking}

セキュリティー担当者、監査員、または管理者として、お客様は {{site.data.keyword.at_full}} サービスを使用して、ユーザーおよびアプリケーションが {{site.data.keyword.Bluemix_notm}} Identity and Access Management (IAM) とどのように対話しているかをトラッキングすることができます。
{:shortdesc}

2019 年 5 月 9 日以降、{{site.data.keyword.cloudaccesstraillong}} サービスは非推奨になりました。IAM イベントのトラッキングを続行するには、お客様のアカウントで {{site.data.keyword.at_short}} のインスタンスを作成する必要があります。詳しくは、[Deprecation of the IBM Cloud Activity Tracker service](https://www.ibm.com/blogs/bluemix/2019/04/deprecating-ibm-cloud-activity-tracker/){: new_window} ![外部リンク・アイコン](../icons/launch-glyph.svg "外部リンク・アイコン") を参照してください。
{: deprecated}

以下のイベントをトラッキングできます。

* グループの作成と削除、またはユーザーの追加と削除によるアクセス・グループの管理
* サービス ID の作成、更新、または削除
* API キーの作成、更新、または削除
* アクセス・ポリシーの作成、更新、または削除
* API キー、許可コード、パスコード、パスワードを使用するか、サービス ID に関連付けられた API キーを使用した {{site.data.keyword.Bluemix_notm}} へのログイン

ユーザーのアクションのモニターを開始するには、[{{site.data.keyword.at_short}}](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-getting-started#getting-started)を参照してください。 トラッキングできる各イベントについて詳しくは、[IAM イベント](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-at_events_iam)を参照してください。
