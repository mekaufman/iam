---

copyright:

  years: 2018, 2019

lastupdated: "2019-01-28"

keywords: parent user, change parent user, classic infrastructure hierarchy

subcollection: iam

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:tip: .tip}

# 更新使用者的母項使用者
{: #update-parent}

如果您具有正確的存取權，則可以更新使用者的母項。當使用者清單可見性設定設為受限時，更新母項使用者會影響使用者如何看到帳戶中的其他使用者。使用者只能看到其為母項的其他使用者，以及母項使用者的這些後代所邀請的任何其他使用者。
{:shortdesc}

請參閱[使用者清單可見性設定](/docs/iam?topic=iam-userlistview#userlistview)，以取得設定的詳細資料。

如果您具有下列存取權，則可以更新另一位使用者的母項：

* 「使用者管理服務」上具有「編輯者」或更高角色的 IAM 原則。
* 您是使用者之標準基礎架構階層中的上代，而且您已獲指派「管理使用者」標準基礎架構許可權。


若要更新使用者的母項，請完成下列步驟：

1. 從功能表列按一下**管理** &gt; **存取 (IAM)**，然後選取**使用者**。  
2. 從清單選取使用者名稱。
3. 從「使用者詳細資料」頁面中，選取**母項**功能表中的新母項使用者。
4. 按一下**套用**。
