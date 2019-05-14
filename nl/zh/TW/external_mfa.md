---

copyright:

  years: 2018, 2019

lastupdated: "2019-05-01"

keywords: MFA, multifactor authentication, external authentication, order authentication, Symantec, phone-based authentication, cancel authentication order

subcollection: iam

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:tip: .tip}

# 訂購使用者的外部鑑別 MFA
{: #external}

當您作為具有正確存取權的管理者時，可以訂購外部鑑別，並針對使用者的登入啟用多因子鑑別 (MFA) 選項。會向您收取外部鑑別選項的每月費用。與 ID 型 MFA 不同，只有已啟用此設定的帳戶，才需要這類型的多因子鑑別 (MFA)。如需相關資訊，請參閱[多因子鑑別的類型](/docs/iam?topic=iam-types#types)。
{:shortdesc}

## 訂購外部鑑別
{: #ordering}

如果您具有下列任何存取權，則可以為使用者訂購外部鑑別：

* 「使用者管理服務」上的「編輯者」或更高角色。
* 您是使用者之標準基礎架構階層中的上代，而且您已獲指派「管理使用者」標準基礎架構許可權。

若要訂購外部鑑別，請完成下列步驟：

1. 從功能表列按一下**管理** &gt; **存取 (IAM)**，然後選取**使用者**。
2. 從清單選取使用者。
3. 從**使用者詳細資料**頁面中，選取「管理使用者的登入」區段中的**訂購外部鑑別**。
4. 選取 **Symantec 身分保護**或**電話型身分保護**。
    * 對於 Symantec 鑑別，使用者必須下載 [Symantec VIP](https://vip.symantec.com/){: new_window} ![外部鏈結圖示](../icons/launch-glyph.svg) 應用程式，並取得認證 ID，才能繼續進行訂購處理程序。
    * 對於電話型鑑別，您可以繼續進行訂購，但是您的使用者必須先[設定配置](/docs/account?topic=account-third-party-MFA#setting-up-phone-based-authentication)，您才能啟用此選項。
5. 根據您的選擇，在下訂單之前，請遵循提示來檢閱價格及條款。
6. 按一下**訂購**，以完成您的選擇。

訂購 Symantec 鑑別之後，您可以從「使用者詳細資料」頁面中為使用者開啟此選項。而且，在訂購電話型鑑別並由使用者進行配置之後，您可以從「使用者詳細資料」頁面中為使用者開啟此選項。

## 停用外部鑑別選項
{: #disable}

您可以隨時停用使用者的 Symantec 或電話型 MFA。

1. 從功能表列按一下**管理** &gt; **存取 (IAM)**，然後選取**使用者**。
2. 從清單選取使用者。
3. 從**使用者詳細資料**頁面中，將 **Symantec 鑑別**或**電話型鑑別**選項設為關閉。

## 取消外部鑑別選項
{: #cancel}

如果您具有正確的存取權，則隨時可以取消外部鑑別的訂單。您可以選擇在沒有退款的情況下立即取消，也可以選擇在您訂購它滿一年時予以取消。

若要取消外部鑑別的訂單，您必須是帳戶擁有者或具有下列所有存取權：

* 管理使用者標準基礎架構許可權
* 取消服務標準基礎架構許可權
* 「支援中心」帳戶管理服務的管理者，或[已移轉的許可權存取群組](/docs/iam?topic=iam-predefined#predefined)內無法使用的檢視、編輯及新增問題單已移轉標準基礎架構許可權。

若要取消外部鑑別訂單，請完成下列步驟：

1. 從功能表列按一下**管理** &gt; **存取 (IAM)**，然後選取「使用者」。
2. 從清單選取使用者。
3. 從**使用者詳細資料**頁面中，按一下 **Symantec 鑑別**或**電話型鑑別**列（取決於您所訂購的項目）的**刪除** ![「刪除」圖示](../icons/icon_trash.svg)。
4. 選取要移除它的時間。
5. 按一下**移除**。
