---

copyright:

  years: 2017, 2019

lastupdated: "2019-03-19"

keywords: SoftLayer permissions, classic infrastructure access, classic infrastructure permission, migrated SoftLayer permissions, migrated permission access group

subcollection: iam

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:important: .important}
{:new_window: target="_blank"}

# Berechtigungen für die klassische Infrastruktur
{: #infrapermission}

Wenn Sie einen Benutzer zu Ihrem Konto einladen, können Sie zwischen drei Berechtigungssets für die klassische Infrastruktur wählen, mit denen eine Massenzuweisung des Zugriffs erfolgt: 'Nur anzeigen', 'Basisbenutzer' und 'Superuser'.
{:shortdesc}

Sie können zusätzliche Berechtigungen festlegen, nachdem der Benutzer die Einladung angenommen hat. Mit dem Ausgangsberechtigungsset, das der Einladung zugewiesen ist, wird beispielsweise kein Zugriff auf Geräte erteilt. Daher müssen Sie den Gerätezugriff erteilen, nachdem der Benutzer die Einladung akzeptiert hat. Weitere Informationen hierzu enthält der Abschnitt [Zugriff auf die klassische Infrastruktur verwalten](/docs/iam/mnginfra.html#mngclassicinfra).

Wenn Sie jemanden zum Konto einladen, können nur Sie, der Kontoeigner, oder ein Benutzer mit der Berechtigung der klassischen Infrastruktur zum Verwalten von Benutzern die Berechtigungen für den Benutzer anpassen. Wenn Sie die Berechtigungen zuweisen und nicht der Kontoeigner sind, können Sie nur die Berechtigungsebene oder eine Untergruppe der bereits zugewiesenen Berechtigungen zuweisen. Ein Kontoeigner kann die Berechtigungen eines jeden Benutzers in dem Konto so aktualisieren, dass der Benutzer eine beliebige Zugriffsebene erhält.


## Migrierte Berechtigungen der klassischen Infrastruktur
{: #predefined}

Eine Reihe von Berechtigungen der klassischen Infrastruktur zum Anzeigen und Verwalten von Abrechnungsinformationen und zum Arbeiten mit Supportfällen wird jetzt zu Zugriffsgruppen migriert. Die Benutzer in Ihrem Konto, denen zuvor diese Berechtigungen zugewiesen waren, werden nun der jeweiligen Zugriffsgruppe für die migrierte Berechtigung zugewiesen. Demzufolge können Berechtigungen für die klassische Infrastruktur jetzt mithilfe von IAM-Zugriffsrichtlinien direkt verwaltet werden.

Diese speziellen Zugriffsgruppe beziehen alle entsprechenden IAM-Richtlinien ein, damit das ursprüngliche Verhalten der Berechtigungen für die klassische Infrastruktur beibehalten wird. Damit zum Beispiel ein Benutzer für einen Supportfall auch weiterhin alle Aktualisierungen aller Benutzer sehen kann, beziehen die Zugriffsgruppen für migrierte Berechtigungen bei den Ticketing-Berechtigungen für die klassische Infrastruktur eine zusätzliche IAM-Richtlinie für den Benutzermanagementservice mit der zugeordneten Rolle als Anzeigeberechtigter (Viewer) ein. Weitere Informationen finden Sie in [Benutzerzugriff für die Arbeit mit Supportfällen zuweisen](/docs/get-support/support_access.html#access).

Sie können diese migrierten Berechtigungen für die klassische Infrastruktur für Benutzer direkt über IAM verwalten, indem Sie sie zu den Zugriffsgruppen für migrierte Berechtigungen hinzufügen bzw. aus ihnen entfernen. Die Richtlinien, die für diese Zugriffsgruppen gelten, sind gesperrt, damit das Zugriffsverhalten für die Gruppenmitglieder beibehalten wird. Sie sollten diese Zugriffsgruppen nicht löschen, damit der Bedienungskomfort auch gegenüber neueren IAM-Benutzern gewahrt bleibt.

Nach der Migration Ihrer Berechtigungen der klassischen Infrastruktur dürfen Sie diese Berechtigungen nicht mehr verwenden. In der folgenden Tabelle sind alle migrierten Berechtigungen für die klassische Infrastruktur aufgeführt, die nun Teil von IAM-Zugriffsgruppen sind.
{: important}

| Name der Zugriffsgruppe für migrierte Berechtigungen | Zulässige Aktionen |
|----------|---------|
| Kontozusammenfassung anzeigen | Anzeigen der Seite 'Konto - Zusammenfassung' und Anzeigen von Rechnungen sowie Zahlungen |
| Compliance-Bericht abrufen | Anfordern eines Compliance-Berichts |
| Unternehmensprofil bearbeiten | Bearbeiten der Informationen zum Unternehmensprofil |
| Einmalige Zahlungen | Durchführen einmaliger Zahlungen für das Benutzerkonto |
| Zahlungsdetails aktualisieren | Aktualisieren der Informationen für wiederkehrende monatliche Zahlungen |
| Einschränkung von Fällen auf die EU begrenzen | Aktivieren oder Inaktivieren der von der EU unterstützten Option, die Daten für Supportfälle auf die Europäische Union beschränkt  |
| Fälle hinzufügen und Bestellungen anzeigen | Erstellen von Supportfällen und Anzeigen aller Bestellungen  |
| Fälle bearbeiten | Bearbeiten beliebiger Supportfälle |
| Fälle durchsuchen | Durchsuchen aller Supportfälle, solange die Berechtigung zum Anzeigen von Fällen ebenfalls zugewiesen ist |
| Fälle anzeigen | Anzeigen aller Supportfälle |
{: caption="Tabelle 1. Vordefinierte Zugriffsgruppen" caption-side="top"}

Sie können die Benutzer für die Zugriffsgruppen auch weiterhin verwalten. Es kann jedoch hilfreich sein, neue Zugriffsgruppen zu erstellen, die eine Kombination von Zugriffsrichtlinien für die [IAM-Kontoverwaltungsservices](/docs/iam?topic=iam-account-services#account-services) einschließen, um das Zuweisen von Zugriff für Kontoverwaltungstasks und das Arbeiten mit Supportfällen zu vereinfachen.
