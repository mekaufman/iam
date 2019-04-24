---

copyright:

  years: 2017, 2019

lastupdated: "2019-01-30"

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:tip: .tip}
{:note: .note}


# 授與服務之間的存取權
{: #serviceauth}

{{site.data.keyword.Bluemix_notm}} Identity and Access Management (IAM) 系統的許多功能，都著重在管理及施行使用者和其應用程式對 {{site.data.keyword.Bluemix_notm}} 資源的存取。不過，在其他情況下，您可能需要提供一個服務來存取另一個服務中的使用者資源。您帳戶中的所有使用者都可以建立授權，但只有具有「管理者」角色的使用者才能刪除授權。您可以在**授權**頁面上，設定及檢視帳戶內已授與的授權。
{:shortdesc}

## 建立授權
{: #create-auth}

您只能授與您為目標服務使用者時的存取層次。例如，如果您對即將存取的服務只具有檢視者存取權，則只能指派檢視者角色來進行授權。

1. 從功能表列按一下**管理** &gt; **存取 (IAM)**，然後選取**授權**。 
2. 按一下**建立**。
3. 選取授權的來源及目標服務。來源服務會獲授與所選取目標服務的存取權。
4. 選取角色，以指派存取目標服務時的來源服務存取權。
5. 按一下**授權**。

只有容許授與這類存取權的服務才能作為選項。
{: note}

## 移除授權
{: #remove-auth}

1. 從功能表列按一下**管理** &gt; **存取 (IAM)**，然後選取**授權**。 
2. 識別您要從帳戶移除之授權的列。
3. 從**動作** ![「動作清單」圖示](../icons/action-menu-icon.svg) 功能表中，選取**移除**。
5. 選取**移除**。
