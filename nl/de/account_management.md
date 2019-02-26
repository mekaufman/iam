---

copyright:

  years: 2019

lastupdated: "2019-02-11"

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:tip: .tip}
{:note: .note}

# Zugriff auf Kontoverwaltungsservices zuweisen
{: #account-services}

Als Kontoeigner oder Administrator eines Kontoverwaltungsservice können Sie Benutzern im Konto mithilfe der Kontoverwaltungsservices die Berechtigung erteilten, Benutzer zum Konto einzuladen, die Abrechnungs- und Nutzungsverfolgung zu verwenden und mit Supportfällen zu arbeiten. Benutzer mit Zugriff können außerdem Service-IDs, Zugriffsrichtlinien und Zugriffsgruppen verwalten.

## Richtlinien für den Zugriff auf den Kontoverwaltungsservice erstellen
{: #account-management-access}

Führen Sie die folgenden Schritte aus, um Zugriff auf einen oder alle Kontoverwaltungsservices zu erteilen:

1. Klicken Sie in der Menüleiste auf **Verwalten** &gt; **Zugriff (IAM)** und wählen Sie anschließend **Benutzer** aus.
2. Wählen Sie in der Zeile für den Benutzer, dem Sie Zugriffsberechtigungen zuweisen wollen, das Menü **Aktionen** ![Symbol für Aktionsliste](../icons/action-menu-icon.svg) aus und klicken Sie dann auf **Zugriff zuweisen**.
3. Wählen Sie diese Option aus, um Zugriff auf **Kontoverwaltungsservices** zu erteilen.
4. Wählen Sie **Alle Kontoverwaltungsservices** oder einen bestimmten Kontoverwaltungsservice aus.
5. Wählen Sie eine beliebige Zusammenstellung von Rollen aus, um die gewünschten Zugriffsberechtigungen zuzuweisen.

Um einem weiteren Benutzer uneingeschränkten Zugriff auf das Konto zum Zweck der Verwaltung des Benutzerzugriffs und der Verwaltung aller Kontoressourcen zu erteilen, müssen Sie zwei Richtlinien zuweisen. Eine Richtlinie, die dem Benutzer Zugriff auf alle Ressourcen im Konto gibt, indem Sie **Alle Services mit aktiviertem Identity and Access Management** mit zugewiesener Rolle **Administrator** auswählen. Zusätzlich eine Richtlinie, die dem Benutzer Zugriff auf alle Kontoverwaltungsservices im Konto gibt, indem Sie **Alle Kontoverwaltungsservices** mit zugewiesener Rolle **Administrator** auswählen.
{: tip}

## Zuordnungen von Aktionen zu Rollen für Kontoverwaltungsservices
{: #account-management-actions-roles}

Die folgenden Tabellen umreißen die Aktionen, die Benutzer ausführen können, wenn ihnen eine bestimmte Rolle für jeden Kontoverwaltungsservices zugewiesen ist. Überprüfen Sie die Informationen, um sicherzustellen, dass Sie Ihren Benutzern die richtige Zugriffsebene zuweisen. 

| Rollen | Aktionen |
|:-------|----------|
| Anzeigeberechtigter |   Zugriffsgruppen und Mitglieder anzeigen     |
| Bediener | Nicht zutreffend    |
| Bearbeiter |  Gruppen anzeigen, erstellen, bearbeiten und löschen <br><br> Benutzer zu Gruppen hinzufügen oder daraus entfernen     |
| Administrator |  Gruppen anzeigen, erstellen, bearbeiten und löschen <br><br> Benutzer hinzufügen oder entfernen <br><br> Zugriff auf eine Gruppe zuweisen <br><br> Zugriff für die Arbeit mit Zugriffsgruppen verwalten   |
{: caption="Tabelle 1. Rollen und Beispielaktionen für den Zugriffsgruppenservice" caption-side="top"}

| Rollen | Aktionen |
|:-------|----------|
| Anzeigeberechtigter |  Benutzer im Konto anzeigen <br><br> Benutzerprofileinstellungen anzeigen     |
| Bediener | Benutzer im Konto anzeigen <br><br> Benutzerprofileinstellungen anzeigen  |
| Bearbeiter |  Benutzer im Konto anzeigen, einladen, entfernen und aktualisieren <br><br> Benutzerprofileinstellungen anzeigen und aktualisieren    |
| Administrator | Benutzer im Konto anzeigen, einladen, entfernen und aktualisieren <br><br> Benutzerprofileinstellungen anzeigen und aktualisieren    |
{: caption="Tabelle 2. Rollen und Beispielaktionen für den Benutzermanagementservice" caption-side="top"}

| Rollen | Aktionen |
|:-------|----------|
| Anzeigeberechtigter |  Fälle anzeigen <br><br> Fälle durchsuchen      |
| Bediener |  Nicht zutreffend    |
| Bearbeiter |  Fälle anzeigen <br><br> Fälle durchsuchen <br><br> Fälle aktualisieren <br><br> Fälle erstellen     |
| Administrator |  Fälle anzeigen <br><br> Fälle durchsuchen <br><br> Fälle aktualisieren <br><br> Fälle erstellen    |
{: caption="Tabelle 3. Rollen und Beispielaktionen für den Support Center-Service" caption-side="top"}

| Rollen | Aktionen |
|:-------|----------|
| Anzeigeberechtigter | Funktionseinstellungen für das Konto anzeigen <br><br> Abonnements im Konto anzeigen <br><br> Kontonamen anzeigen <br><br> Ressourcengruppen anzeigen   |
| Bediener | Funktionseinstellungen für das Konto anzeigen <br><br> Abonnements im Konto anzeigen <br><br> Kontonamen anzeigen und ändern <br><br> Ressourcengruppen anzeigen und aktualisieren    |
| Bearbeiter |  Funktionseinstellungen für das Konto anzeigen und aktualisieren <br><br> Abonnements im Konto anzeigen <br><br> Angebote im Konto anzeigen <br><br> Funktionscodes anzeigen und anwenden <br><br> Kontonamen anzeigen und ändern <br><br> Ausgabenlimits anzeigen und aktualisieren <br><br> Ressourcengruppen anzeigen, erstellen und aktualisieren    |
| Administrator |  Funktionseinstellungen für das Konto anzeigen und aktualisieren <br><br> Abonnements im Konto anzeigen <br><br> Angebote im Konto anzeigen <br><br> Funktionscodes anzeigen und anwenden <br><br> Kontonamen anzeigen und ändern <br><br> Ausgabenlimits anzeigen und aktualisieren <br><br> Kontostand für Abonnements und Nutzungsverfolgung anzeigen <br><br> Zugriff zum Verwalten von Ressourcengruppen anzeigen, erstellen, aktualisieren und zuweisen  |
{: caption="Tabelle 4. Rollen und Beispielaktionen für den Abrechnungsservice" caption-side="top"}

| Rollen | Aktionen |
|:-------|----------|
| Anzeigeberechtigter |   IDs anzeigen     |
| Bediener | IDs und API-Schlüssel erstellen und löschen   |
| Bearbeiter |  IDs und API-Schlüssel erstellen, aktualisieren und löschen  |
| Administrator |  IDs und API-Schlüssel erstellen, aktualisieren und löschen <br><br> Zugriffsrichtlinien zu IDs zuweisen  |
{: caption="Tabelle 5. Rollen und Beispielaktionen für den IAM Identity Service" caption-side="top"}

Für den IAM Identity Service können diese Aktionen auf Service-IDs innerhalb des Kontos angewendet werden, die nicht vom Benutzer erstellt wurden. Alle Benutzer können Service-IDs erstellen. Sie fungieren als Administratoren für diese IDs und können den zugehörigen API-Schlüssel und Zugriffsrichtlinien erstellen. Dieser Kontoverwaltungsservice bezieht sich jedoch auf die Fähigkeit zum Anzeigen, Löschen und Zuweisen von Zugriff auf Service-IDs im Konto, die von anderen Benutzern erstellt wurden.
{: note}

| Rollen | Aktionen |
|:-------|----------|
| Anzeigeberechtigter |   Private Services anzeigen    |
| Bediener | Nicht zutreffend    |
| Bearbeiter | Objektmetadaten ändern, nicht jedoch die Sichtbarkeit privater Services |
| Administrator | Objektmetadaten oder Sichtbarkeit privater Services ändern, Sichtbarkeit eines öffentlichen Service einschränken |
{: caption="Tabelle 6. Rollen und Beispielaktionen für den Global Catalog-Service" caption-side="top"}

| Rollen | Aktionen |
|:-------|----------|
| Anzeigeberechtigter |  Alle Rollenaktionen von Anzeigeberechtigten für die Kontoverwaltungsservices     |
| Bediener |  Alle Rollenaktionen von Bedienern für die Kontoverwaltungsservices     |
| Bearbeiter |  Alle Rollenaktionen von Bearbeitern für die Kontoverwaltungsservices     |
| Administrator |  Alle Rollenaktionen von Administratoren für die Kontoverwaltungsservices   |
{: caption="Tabelle 7. Rollen und Beispielaktionen für eine Richtlinie für alle Identitäts- und Zugriffsservices" caption-side="top"}
