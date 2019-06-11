---

copyright:

  years: 2018, 2019

lastupdated: "2019-05-16"

keywords: remove user, delete user, user management

subcollection: iam

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:tip: .tip}

# 移除使用者
{: #remove}

當您從帳戶移除使用者時，使用者就無法再登入主控台；如果使用者仍屬於其他帳戶，則請切換至您的帳戶；或是無法再存取帳戶資源。
{:shortdesc}

只有帳戶擁有者或具有下列存取權的使用者，才能從帳戶移除使用者：

* 具有已指派「管理者」角色之「使用者管理」帳戶管理服務的 IAM 原則，以及 Cloud Foundry 組織管理員（如果使用者屬於 Cloud Foundry 組織）。
* 如果您的帳戶中有標準基礎架構，則使用者必須具有已指派「管理者」角色之「使用者管理」帳戶管理服務的 IAM 原則、必須為 Cloud Foundry 組織管理員（如果使用者屬於 Cloud Foundry 組織），以及必須為已指派「管理使用者」標準基礎架構許可權之標準基礎架構使用者階層中的使用者上代。

若要從帳戶移除使用者，請完成下列步驟：

1. 從功能表列按一下**管理** &gt; **存取 (IAM)**，然後選取**使用者**。
2. 從您要移除的使用者列中，選取**動作** ![「動作清單」圖示](../icons/action-menu-icon.svg) 功能表中的**移除使用者**。

如果您收到無法移除標準基礎架構使用者的錯誤訊息，請確定該使用者在使用者階層中的所有後代皆[指派了新母項](/docs/iam?topic=iam-update-parent)、[已在帳戶中停用](/docs/iam?topic=iam-status)或已刪除，然後再試一次。
{: tip}
