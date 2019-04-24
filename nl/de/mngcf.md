---

copyright:

  years: 2017, 2019

lastupdated: "2019-01-28"

keywords: Cloud Foundry access, assign access, add user to organization, Cloud Foundry roles

subcollection: iam

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}

# Cloud Foundry-Zugriff verwalten
{: #mngcf}

Um den Zugriff auf Kontoorganisationen und die entsprechenden Bereiche verwalten zu können, müssen Sie der Kontoeigner, Organisations- oder Bereichsmanager sein.
{:shortdesc}

## Cloud Foundry-Zugriff aktualisieren
{: #update_cf_access}

1. Klicken Sie in der Menüleiste auf **Verwalten** &gt; **Zugriff (IAM)** und wählen Sie **Benutzer** aus.
2. Wählen Sie in der Zeile für den Benutzer, dem Sie Zugriffsberechtigungen zuweisen wollen, das Menü **Aktionen** ![Symbol für Aktionsliste](../icons/action-menu-icon.svg) aus und klicken Sie dann auf **Zugriff zuweisen**.
3. Wählen Sie die Option zum **Zuweisen mit Cloud Foundry** aus.
4. Erweitern Sie die Ansicht der Zeile für die Organisation, der der Benutzer zugewiesen ist, um die Zugriffsberechtigungen des Benutzers auf Bereiche und die zugehörigen Rollen in diesen Bereichen anzuzeigen.
5. Über das Menü **Aktionen** ![List of actions icon](../icons/action-menu-icon.svg) im Abschnitt zu Cloud Foundry können Sie folgende Aktionen ausführen:

  * Benutzer aus der Organisation entfernen
  * Organisationsrolle bearbeiten
  * Bereichsrolle bearbeiten

## Benutzer einer Organisation hinzufügen
{: #add_to_org}

Wenn Sie der Manager einer Organisation sind, deren Mitglied der Benutzer noch nicht ist, dann müssen Sie den Benutzer der betreffenden Organisation zuweisen.

1. Klicken Sie in der Menüleiste auf **Verwalten** &gt; **Zugriff (IAM)** und wählen Sie **Benutzer** aus.
2. Wählen Sie in der Zeile für den Benutzer, dem Sie Zugriffsberechtigungen zuweisen wollen, das Menü **Aktionen** ![Symbol für Aktionsliste](../icons/action-menu-icon.svg) aus und klicken Sie dann auf **Zugriff zuweisen**.
3. Wählen Sie die Option zum **Zuweisen mit Cloud Foundry** aus.
4. Wählen Sie **Organisation zuweisen** aus.
5. Weisen Sie dem Benutzer die gewünschten Zugriffsberechtigungen zu:
   * Wählen Sie eine Organisation aus, der der Benutzer hinzugefügt werden soll.
   * Weisen Sie eine Organisationsrolle zu.
   * Wählen Sie eine Region aus.
   * Wählen Sie einen Bereich aus.
   * Weisen Sie eine Bereichsrolle zu.
7. Klicken Sie auf **Zuweisen**.

## Zugewiesene Zugriffsberechtigungen überprüfen
{: #review_my_access}

Wenn Sie Ihre zugewiesenen Zugriffsberechtigungen in einem Konto überprüfen müssen, zu dem Sie hinzugefügt wurden, führen Sie die folgenden Schritte aus:

1. Klicken Sie in der Menüleiste auf **Verwalten** &gt; **Zugriff (IAM)** und wählen Sie **Benutzer** aus.
2. Wählen Sie Ihren Namen aus.
3. Klicken Sie auf **Cloud Foundry-Zugriff**.
3. Erweitern Sie die Zeile 'Organisation' und überprüfen Sie die Ihnen zugewiesenen Rollen.

Wenn Sie weiterführende Zugriffsberechtigungen benötigen, müssen Sie sich an den Organisationsmanager oder den Kontoeigner wenden, um Ihre zugewiesene Cloud Foundry-Rolle zu aktualisieren.
