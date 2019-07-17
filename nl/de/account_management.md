---

copyright:

  years: 2019

lastupdated: "2019-07-01"

keywords: account management, access, access policy, account administrator, user management, account management services, use account management services to grant users in the account access to invite users to the account, billing service, support center service, identity service, global catalog service, enterprise service

subcollection: iam

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:tip: .tip}
{:note: .note}

# Zugriffsberechtigungen für Kontoverwaltungsservices zuweisen
{: #account-services}

Als Kontoeigner oder Administrator eines Kontoverwaltungsservice können Sie diese Services verwenden, um Benutzern die Zugriffsberechtigung zu erteilen, mit der sie z. B. Benutzer zum Konto einladen, Abrechnung und Nutzung verfolgen und mit Supportfällen arbeiten können. Benutzer mit den entsprechenden Zugriffsrichtlinien für die Kontoverwaltung können darüber hinaus Service-IDs, Zugriffsrichtlinien, Katalogeinträge und Zugriffsgruppen verwalten.
{:shortdesc}

## Richtlinien für den Zugriff auf den Kontoverwaltungsservice erstellen
{: #account-management-access}

Führen Sie die folgenden Schritte aus, um Zugriff auf einen oder alle Kontoverwaltungsservices zu erteilen:

1. Klicken Sie in der Menüleiste auf **Verwalten** &gt; **Zugriff (IAM)** und wählen Sie anschließend **Benutzer** aus.
2. Wählen Sie in der Zeile für den Benutzer, dem Sie Zugriffsberechtigungen zuweisen wollen, das Menü **Aktionen** ![Symbol für Aktionsliste](../icons/action-menu-icon.svg) aus und klicken Sie dann auf **Zugriff zuweisen**.
3. Wählen Sie diese Option aus, um Zugriff auf **Kontoverwaltungsservices** zu erteilen.
4. Wählen Sie **Alle Kontoverwaltungsservices** oder einen bestimmten Kontoverwaltungsservice aus.
5. Wählen Sie eine beliebige Zusammenstellung von Rollen aus, um die gewünschten Zugriffsberechtigungen zuzuweisen.

Um einem weiteren Benutzer uneingeschränkten Zugriff auf das Konto zum Zweck der Verwaltung des Benutzerzugriffs und der Verwaltung aller Kontoressourcen zu erteilen, müssen Sie zwei Richtlinien zuweisen. Eine Richtlinie, die dem Benutzer Zugriff auf alle Ressourcen im Konto ermöglicht, indem Sie **Alle für IAM aktivierten Services** mit den zugewiesenen Rollen **Administrator** und **Manager** auswählen. Zusätzlich eine Richtlinie, die dem Benutzer Zugriff auf alle Kontoverwaltungsservices im Konto ermöglicht, indem Sie **Alle Kontoverwaltungsservices** mit zugewiesener Rolle **Administrator** auswählen.
{: tip}

## Aktionen und Rollen für Kontoverwaltungservices
{: #account-management-actions-roles}

Die folgenden Tabellen umreißen die Aktionen, die Benutzer ausführen können, wenn ihnen eine bestimmte Rolle für jeden Kontoverwaltungsservices zugewiesen ist. Überprüfen Sie die Informationen, um sicherzustellen, dass Sie Ihren Benutzern die richtige Zugriffsebene zuweisen. 

### IAM-Zugriffsgruppenservice
{: #access-groups-account-management}

Sie können Benutzern die Zugriffsberechtigung zum Anzeigen, Erstellen, Bearbeiten und Löschen von Zugriffsgruppen im Konto mithilfe des Kontoverwaltungsservice für Zugriffsgruppen erteilen.  

| Rollen | Aktionen |
|:-------|----------|
| Anzeigeberechtigter |   Zugriffsgruppen und Mitglieder anzeigen     |
| Operator | Nicht zutreffend    |
| Bearbeiter |  Gruppen anzeigen, erstellen, bearbeiten und löschen <br><br> Benutzer zu Gruppen hinzufügen oder daraus entfernen     |
| Administrator |  Gruppen anzeigen, erstellen, bearbeiten und löschen <br><br> Benutzer hinzufügen oder entfernen <br><br> Zugriff auf eine Gruppe zuweisen <br><br> Zugriff für die Arbeit mit Zugriffsgruppen verwalten   |
{: caption="Tabelle 1. Rollen und Beispielaktionen für den Zugriffsgruppenservice" caption-side="top"}

### Benutzerverwaltung
{: #user-management-account-management}

Sie können Benutzern die Zugriffsberechtigung zum Anzeigen von Benutzern in einem Konto, zum Einladen und Entfernen von Benutzern sowie zum Anzeigen und Aktualisieren von Benutzerprofileinstellungen mithilfe des Kontoverwaltungsservice für die Benutzerverwaltung erteilen.  

| Rollen | Aktionen |
|:-------|----------|
| Anzeigeberechtigter |  Benutzer im Konto anzeigen <br><br> Benutzerprofileinstellungen anzeigen     |
| Operator | Benutzer im Konto anzeigen <br><br> Benutzerprofileinstellungen anzeigen  |
| Bearbeiter |  Benutzer im Konto anzeigen, einladen, entfernen und aktualisieren <br><br> Benutzerprofileinstellungen anzeigen und aktualisieren    |
| Administrator | Benutzer im Konto anzeigen, einladen, entfernen und aktualisieren <br><br> Benutzerprofileinstellungen anzeigen und aktualisieren    |
{: caption="Tabelle 2. Rollen und Beispielaktionen für den Benutzerverwaltungsservice" caption-side="top"}

Die Rolle des Anzeigeberechtigten im Benutzerverwaltungsservice ist eine häufig zugewiesene Rolle für Benutzer, denen auch eine Rolle zum Anzeigen oder Verwalten von Supportfällen zugewiesen wird. Der Grund hierfür ist, dass bei einer Einschränkung der Benutzerlistenanzeige in den IAM-Einstellungen durch den Kontoeigner Benutzer Supportfälle, die von anderen Benutzern im Konto geöffnet werden, möglicherweise nicht anzeigen können. Wird ihnen jedoch die Rolle des Anzeigeberechtigten für den Benutzerverwaltungsservice zugewiesen, hat die Einstellung für die Benutzerlistenanzeige keinen Einfluss darauf, ob sie Fälle im Konto anzeigen können.
{: tip}

### Support Center
{: #support-center-account-management}

Sie können Benutzern die Zugriffsberechtigung für die Verwaltung von Supportfällen mithilfe des Support Center-Service erteilen. 

| Rollen | Aktionen |
|:-------|----------|
| Anzeigeberechtigter |  Fälle anzeigen <br><br> Fälle durchsuchen      |
| Operator |  Nicht zutreffend    |
| Bearbeiter |  Fälle anzeigen <br><br> Fälle durchsuchen <br><br> Fälle aktualisieren <br><br> Fälle erstellen     |
| Administrator |  Fälle anzeigen <br><br> Fälle durchsuchen <br><br> Fälle aktualisieren <br><br> Fälle erstellen    |
{: caption="Tabelle 3. Rollen und Beispielaktionen für den Support Center-Service" caption-side="top"}

Im Allgemeinen wird Benutzern die Rolle eines Anzeigeberechtigten für den Benutzerverwaltungsservice zusätzlich zu einer Zugriffsrichtlinie für das Support Center zugewiesen, um sicherzustellen, dass die Benutzer alle Fälle im Konto anzeigen können, unabhängig davon, welche Einstellungen der Kontoeigner für die Benutzerlistenanzeige festgelegt hat. Wenn in den Einstellungen eine eingeschränkte Benutzerlistenanzeige festgelegt ist, damit Benutzer andere Benutzer im Konto nicht anzeigen können, kann dies die Möglichkeit eines Benutzers einschränken, Supportfälle in einem Konto anzuzeigen, zu durchsuchen und zu verwalten, die sie nicht selbst geöffnet haben.
{: tip}

### Abrechnung
{: #billing-acct-mgmt}

Sie können Benutzern die Zugriffsberechtigung für das Aktualisieren von Kontoeinstellungen, das Anzeigen von Abonnements, das Anzeigen von Angeboten, das Anwenden von Feature-Codes, das Aktualisieren von Ausgabegrenzwerten und das Verfolgen der Nutzung mithilfe des Abrechnungsservice erteilen. 

| Rollen | Aktionen |
|:-------|----------|
| Anzeigeberechtigter | Funktionseinstellungen für das Konto anzeigen <br><br> Abonnements im Konto anzeigen <br><br> Kontonamen anzeigen <br><br> Ressourcengruppen anzeigen   |
| Operator | Funktionseinstellungen für das Konto anzeigen <br><br> Abonnements im Konto anzeigen <br><br> Kontonamen anzeigen und ändern <br><br> Ressourcengruppen anzeigen und aktualisieren    |
| Bearbeiter |  Funktionseinstellungen für das Konto anzeigen und aktualisieren <br><br> Abonnements im Konto anzeigen <br><br> Angebote im Konto anzeigen <br><br> Funktionscodes anzeigen und anwenden <br><br> Kontonamen anzeigen und ändern <br><br> Ausgabenlimits anzeigen und aktualisieren <br><br> Ressourcengruppen anzeigen, erstellen und aktualisieren    |
| Administrator |  Funktionseinstellungen für das Konto anzeigen und aktualisieren <br><br> Abonnements im Konto anzeigen <br><br> Angebote im Konto anzeigen <br><br> Funktionscodes anzeigen und anwenden <br><br> Kontonamen anzeigen und ändern <br><br> Ausgabenlimits anzeigen und aktualisieren <br><br> Kontostand für Abonnements und Nutzungsverfolgung anzeigen <br><br> Zugriff zum Verwalten von Ressourcengruppen anzeigen, erstellen, aktualisieren und zuweisen  |
{: caption="Tabelle 4. Rollen und Beispielaktionen für den Abrechnungsservice" caption-side="top"}

### IAM-Identitätsservice
{: #identity-service-account-management}

Sie können Benutzern die Zugriffsberechtigung für das Verwalten von Service-IDs mithilfe des IAM-Identitätsservice erteilen. Für den IAM-Identitätsservice können diese Aktionen auf Service-IDs innerhalb des Kontos angewendet werden, die nicht vom Benutzer erstellt wurden. Alle Benutzer können Service-IDs erstellen. Sie fungieren als Administratoren für diese IDs und können den zugehörigen API-Schlüssel und Zugriffsrichtlinien erstellen. Dieser Kontoverwaltungsservice bezieht sich jedoch auf die Fähigkeit zum Anzeigen, Löschen und Zuweisen von Zugriff auf Service-IDs im Konto, die von anderen Benutzern erstellt wurden.

| Rollen | Aktionen |
|:-------|----------|
| Anzeigeberechtigter |   IDs anzeigen     |
| Operator | IDs und API-Schlüssel erstellen und löschen   |
| Bearbeiter |  IDs und API-Schlüssel erstellen, aktualisieren und löschen  |
| Administrator |  IDs und API-Schlüssel erstellen, aktualisieren und löschen <br><br> Zugriffsrichtlinien zu IDs zuweisen  |
{: caption="Tabelle 5. Rollen und Beispielaktionen für den IAM-Identitätsservice" caption-side="top"}
{: #identity-service-acct-mgmt}


### Globaler Katalog
{: #global-catalog-account-management}

Sie können Benutzern die Zugriffsberechtigung zum Anzeigen privater Services im Katalog oder zum Ändern der Sichtbarkeit privater Services für andere Benutzer mithilfe des Service für den globalen Katalog erteilen. 

| Rollen | Aktionen |
|:-------|----------|
| Anzeigeberechtigter |   Private Services anzeigen    |
| Operator | Nicht zutreffend    |
| Bearbeiter |   Objektmetadaten ändern, nicht jedoch die Sichtbarkeit privater Services     |
| Administrator |  Objektmetadaten oder Sichtbarkeit privater Services ändern, Sichtbarkeit eines öffentlichen Service einschränken   |
{: caption="Tabelle 6. Rollen und Beispielaktionen für den Global Catalog-Service" caption-side="top"}


### Option für alle Kontoverwaltungsservices
{: #all-account-management}

Wenn Sie Benutzern ohne großen Zeitaufwand eine breite Palette vielfältiger Zugriffsberechtigungen für die Kontoverwaltung zuweisen möchten, können Sie eine Richtlinie für die Option für alle Kontoverwaltungsservices zuweisen. Abhängig von der ausgewählten Rolle kann das Subjekt der Richtlinie alle gemäß der ausgewählten Rolle für den jeweiligen Kontoverwaltungsservice gültigen Aktionen ausführen. 


| Rollen | Aktionen |
|:-------|----------|
| Anzeigeberechtigter |  Alle Rollenaktionen von Anzeigeberechtigten für die Kontoverwaltungsservices     |
| Operator |  Alle Rollenaktionen von Operatoren für die Kontoverwaltungsservices     |
| Bearbeiter |  Alle Rollenaktionen von Bearbeitern für die Kontoverwaltungsservices und die Möglichkeit, Ressourcengruppen zu erstellen    |
| Administrator |  Alle Rollenaktionen von Administratoren für die Kontoverwaltungsservices und die Möglichkeit, Ressourcengruppen zu erstellen   |
{: caption="Tabelle 7. Rollen und Beispielaktionen für eine Richtlinie für alle Identitäts- und Zugriffsservices" caption-side="top"}


