---



copyright:

  years: 2015，2019

lastupdated: "2019-02-13"

keywords: dedicated ID, public IBMid, IBMid, public IAM service

subcollection: iam

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:tip: .tip}
{:new_window: target="_blank"}

# 専用 ID とパブリック IBMid との接続
{: #connect_dedicated_id}

パブリック IAM サービスが使用可能な専用クラウドにログインするために、{{site.data.keyword.Bluemix_notm}} CLI では専用 ID ではなくパブリック IBMid でログインするよう要求されます。
{:shortdesc}

```
  $ ibmcloud login -a https://api.{dedicated_env}.cloud.ibm.com
  API endpoint: https://api.{dedicated_env}.cloud.ibm.com

  Public IAM token service is available in the dedicated environment.
  Login with your public IBMid, or use '--no-iam' to login as a dedicated user only.

  Email>
```

専用 ID がパブリック IBMid に既に接続されている場合、認証されてログインされます。

```
  Authenticating...
  OK

  Connected to dedicated user my_dedicated_id
```

しかし、専用 ID がパブリック IBMid に接続されていない場合、パブリック IBMid に手動で接続するようプロンプトが出されます。

```
  You are logging with an IBMid that does not associated with any dedicated user.
  To set up the connection, input the credentials of the dedicated user.

  Choose a credential type:
  1. Username and password
  2. One Time Code (Get one at https://login.{dedicated_env}.cloud.ibm.com/passcode)
  Enter a number>
```

専用 ID の資格情報を入力するオプションを選択します。 認証に成功すると、専用 ID はパブリック IBMid に接続されます。

## ローカル UAA サーバーへのログインの強制
{: #force_login}

専用 ID での UAA サーバーへのログインを強制するには、`ibmcloud login` コマンドに `--no-iam` オプションを指定します。

```
  $ ibmcloud login --no-iam
```

## 専用 ID のパブリック IBMid からの切断
{: #disconnect_id}

`ibmcloud iam dedicated-id-disconnect` を使用して、パブリック IBMid と接続された専用 ID を切断できます。

```
  $ ibmcloud iam dedicated-id-disconnect
  Do you really want to disconnect my_dedicated_id from public IBMid? (Y/N)> y
  Disconnecting dedicated user my_dedicated_id from public IBMid...
  OK

  Logging out...
  OK
```
