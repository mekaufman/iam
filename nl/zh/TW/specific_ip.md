---

copyright:

  years: 2018, 2019

lastupdated: "2019-01-28"

keywords: specific IP addresses, IP addresses, restrict IP access, IP address access, allow IP access

subcollection: iam

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:tip: .tip}
{:note: .note}
{:important: .important}

# 容許使用者的特定 IP 位址
{: #ips}

依預設，所有 IP 位址都可以用來登入 {{site.data.keyword.cloud}} 主控台，以及存取標準基礎架構 API。您可以指定哪些 IP 位址具有存取權，且只能使用容許的指定位址，並限制其他所有 IP 位址。
{:shortdesc}

如果您具有受限 IP 位址，則無法在 [https://cloud.ibm.com](https://cloud.ibm.com){: new_window} ![外部鏈結圖示](../icons/launch-glyph.svg "外部鏈結圖示") 上存取標準基礎架構頁面。您必須前往 [https://control.softlayer.com](https://control.softlayer.com){: new_window} ![外部鏈結圖示](../icons/launch-glyph.svg "外部鏈結圖示")。
{: important}

如果您具有下列指派的存取權，則可以更新另一位使用者的受限 IP 位址：

  * 「使用者管理服務」上具有「編輯者」或更高角色的 IAM 原則。
  * 您是使用者之標準基礎架構階層中的上代，而且您已獲指派「管理使用者」標準基礎架構許可權。

如果您已在「使用者詳細資料」頁面上啟用「使用者管理的登入」設定，則可以自行管理此設定。
{: tip}

若要限制使用者只能使用特定 IP 位址，請完成下列步驟：

1. 從功能表列按一下**管理** &gt; **存取 (IAM)**，然後選取**使用者**。
2. 從清單選取使用者。
3. 從「使用者詳細資料」頁面，移至 **IP 位址限制**區段。
4. 對於**雲端平台**，輸入 IP 位址。列出的 IP 位址是此使用者可以從中登入 {{site.data.keyword.Bluemix}} 的唯一 IP 位址。
5. 對於**標準基礎架構**，輸入 IP 位址。列出的 IP 位址是使用者可以從中呼叫標準基礎架構 API 的唯一 IP 位址。

  若要輸入標準基礎架構 IP 位址，使用者必須已建立標準基礎架構 API 金鑰。
  {: note}
