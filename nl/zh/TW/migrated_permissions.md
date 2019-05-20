---

copyright:

  years: 2019

lastupdated: "2019-05-13"

keywords: migrated permissions, SoftLayer account permissions, migrated permission access group, migrated classic infrastructure permissions

subcollection: iam

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:important: .important}
{:new_window: target="_blank"}


# 管理已移轉 SoftLayer 帳戶許可權
{: #migrated_permissions}

存取群組現在包括一組已移轉的 SoftLayer 帳戶許可權，可用於檢視及管理計費資訊以及使用支援案例。您帳戶中先前獲指派這些許可權的使用者，現在已指派給個別移轉的許可權存取群組。因此，使用 IAM 存取群組，即可直接管理許可權。
{:shortdesc}

這些特殊存取群組包括所有適當的 IAM 原則，以保留 SoftLayer 帳戶許可權的原始行為。例如，若要讓使用者繼續查看支援案例上所有使用者的所有更新，問題單 SoftLayer 帳戶許可權的已移轉許可權存取群組會包括已獲指派「檢視者」角色之「使用者管理服務」上的額外 IAM 原則。如需相關資訊，請參閱[指派使用者存取權以便使用支援案例](/docs/get-support?topic=get-support-access#access)。

您可以繼續透過 IAM 直接管理使用者的這些已移轉標準基礎架構許可權，方法是從已移轉的許可權存取群組中新增及移除使用者。會鎖定這些存取群組所具有的原則，以保留其成員的存取行為。若要維護較新 IAM 使用者的輕鬆使用，請避免刪除這些存取群組。

在您移轉標準基礎架構許可權之後，必須停止使用這些許可權。請參閱下表，以取得現在屬於 IAM 存取群組的所有已移轉標準基礎架構許可權。
{: important}

| 已移轉的許可權存取群組名稱 | 容許的動作 |
|----------|---------|
| 檢視帳戶摘要 | 檢視帳戶摘要頁面以及發票與付款。|
| 取得規範報告 | 要求規範報告。|
| 編輯公司設定檔 | 編輯公司設定檔資訊。|
| 一次性付款 | 在使用者帳戶內進行一次性付款。|
| 更新付款詳細資料 | 更新循環每月付款資訊。|
| 限制 EU 案例限制 | 啟用或停用「歐盟支援」選項，以將支援案例資料限制為「歐盟」。|
| 新增案例以及檢視訂單 | 建立支援案例，以及查看所有訂單。|
| 編輯案例 | 編輯任何支援案例。|
| 搜尋案例 | 如果同時指派檢視案例許可權，則搜尋所有支援案例。|
| 檢視案例 | 檢視所有支援案例。|
{: caption="表 1. 預先定義的存取群組" caption-side="top"}

