---

copyright:

  years: 2018, 2019

lastupdated: "2019-05-01"

keywords: security questions, MFA, multifactor authentication, login security

subcollection: iam

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:tip: .tip}
{:note: .note}

# 啟用使用者的 MFA 安全問題
{: #questions}

當您作為具有正確存取權的管理者時，可以啟用在登入時提示使用者輸入安全問題及回答的選項。只有已啟用此設定的帳戶，才需要這類型的多因子鑑別 (MFA)。與 ID 型 MFA 不同，只有已啟用此設定的帳戶，才需要這類型的多因子鑑別 (MFA)。如需相關資訊，請參閱[多因子鑑別的類型](/docs/iam?topic=iam-types#types)。
{:shortdesc}

如果您具有下列任何存取權，則可以為您帳戶中的其他使用者更新此設定：

* 「使用者管理服務」上的「編輯者」或更高角色。
* 您是使用者之標準基礎架構階層中的上代，而且您已獲指派「管理使用者」標準基礎架構許可權。


若要開啟使用者的這個 MFA 選項，他或她必須先從設定檔「登入設定」頁面[設定安全問題](/docs/account?topic=account-login-settings#security-questions)及回答。
{: note}

1. 從功能表列按一下**管理** &gt; **存取 (IAM)**，然後選取**使用者**。
2. 從清單選取使用者。
3. 從**管理使用者的登入**區段的**使用者詳細資料**頁面中，將**登入時要求 MFA 安全問題**選項設為開啟。

如果您已在「使用者詳細資料」頁面上啟用「使用者管理的登入」設定，則可以自行管理此設定。
{: tip}
