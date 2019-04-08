---

copyright:
  years: 2015, 2019
lastupdated: "2019-04-01"

---

{:tsSymptoms: .tsSymptoms}
{:tsCauses: .tsCauses}
{:tsResolve: .tsResolve}
{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:screen: .screen}
{:codeblock: .codeblock}
{:pre: .pre}
{:note:.deprecated}
{:troubleshoot: data-hd-content-type='troubleshoot'}

# IAM 的疑難排解
{: #troubleshoot_iam}

使用 IAM 的一般問題可能包括需要存取資源或帳戶才能執行作業或識別正確的存取權類型，以便指派您帳戶中的使用者，來執行特定作業。在許多情況下，您可以遵循一些簡單的步驟，從這些問題回復。
{:shortdesc}

## 如何知道我被指派了何種存取權？
{: #troubleshoot-myaccess}
{: troubleshoot}

如果您沒有完成特定作業的存取權，例如建立服務實例並將它新增至資源群組，或是邀請其他使用者加入帳戶，您可能需要檢查您被指派了何種存取權。

我不確定我被指派何種存取層次，以便在所屬帳戶中完成動作。
{: tsSymptoms}
   
您可能未被指派正確的存取權。
{: tsCauses}

若要檢查您可以存取的內容，以及存取層次，請完成下列步驟。如果您需要要求存取，請與帳戶擁有者聯絡。

請移至**管理** &gt; **存取 (IAM)**，然後在**使用者**頁面上選取您的名稱。接著，根據您要尋找的存取權來選取不同的標籤：
{: tsResolve}

* 若要判斷您透過獲指派之存取群組所取得的存取權，請選取**存取群組**。
* 若要查看指派給您的 IAM 存取原則，請選取**存取原則**。
* 若要查看您的 Cloud Foundry 對所有組織及空間的存取權，請選取 **Cloud Foundry 存取**。


## 如何取得存取權以邀請使用者加入帳戶？ 
{: #troubleshoot-invite}
{: troubleshoot}

如果您不是帳戶擁有者，且未被指派正確的存取權，則無法邀請使用者加入帳戶。 

我無法邀請使用者加入帳戶。
{: tsSymptoms}
   
您可能未被指派正確的存取權。
{: tsCauses}

若要邀請使用者並管理未完成的邀請，您必須是帳戶擁有者、組織管理員、含使用者管理帳戶管理服務上具有「編輯者」或更高角色之 IAM 存取原則的使用者，或者必須具有用來新增使用者的標準基礎架構許可權。
{: tsResolve}


## 如何檢視其他使用者的標準基礎架構許可權？
{: #troubleshoot-classicinfra}
{: troubleshoot}

帳戶擁有者具有帳戶的完整存取權，因此他們自己看不到這些許可權。個別使用者無法編輯自己的許可權，因此他們在標準基礎架構頁面上會看到許可權，但無法編輯。您必須有特定的存取權才能檢視及編輯帳戶中另一位使用者的許可權。

您看到訊息指出您無法檢視另一位使用者的標準基礎架構許可權。
{: tsSymptoms}
   
您可能未被指派正確的存取權。
{: tsCauses}

您必須要求帳戶擁有者以便被指派**管理使用者**標準基礎架構許可權，但您也必須是標準基礎架構使用者階層內的使用者上代，才能檢視及管理另一位使用者的許可權。
{: tsResolve}
