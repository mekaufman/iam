---

copyright:

  years: 2019

lastupdated: "2019-05-13"

keywords: migrated permissions, SoftLayer account permissions, migrated permission access group, migrated classic infrastructure permissions

subcollection: iam

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:important: .important}
{:new_window: target="_blank"}


# Migrierte SoftLayer-Kontoberechtigungen verwalten
{: #migrated_permissions}

Zugriffsgruppen umfassen nun eine migrierte Gruppe von SoftLayer-Kontoberechtigungen für die Anzeige und Verwaltung von Abrechnungsinformationen und für die Bearbeitung von Supportfällen. Die Benutzer in Ihrem Konto, denen zuvor diese Berechtigungen zugewiesen waren, werden nun der jeweiligen Zugriffsgruppe für die migrierte Berechtigung zugewiesen. Dies bedeutet, dass die Berechtigungen nun direkt mithilfe von IAM-Zugriffsgruppen verwaltet werden können.
{:shortdesc}

Diese speziellen Zugriffsgruppe beziehen alle entsprechenden IAM-Richtlinien ein, damit das ursprüngliche Verhalten der SoftLayer-Kontoberechtigungen beibehalten wird. Beispiel: Damit ein Benutzer weiterhin alle Aktualisierungen aller Benutzer für einen Supportfall anzeigen kann, enthalten die migrierten Berechtigungszugriffsgruppen für die SoftLayer-Ticketing-Kontoberechtigungen eine zusätzliche IAM-Richtlinie für den Benutzerverwaltungsservice mit der zugewiesenen Rolle eines Anzeigeberechtigten. Weitere Informationen finden Sie in [Benutzerzugriff für die Arbeit mit Supportfällen zuweisen](/docs/get-support?topic=get-support-access#access).

Sie können diese migrierten Berechtigungen für die klassische Infrastruktur für Benutzer direkt über IAM verwalten, indem Sie sie zu den Zugriffsgruppen für migrierte Berechtigungen hinzufügen bzw. aus ihnen entfernen. Die Richtlinien, die für diese Zugriffsgruppen gelten, sind gesperrt, damit das Zugriffsverhalten für die Gruppenmitglieder beibehalten wird. Sie sollten diese Zugriffsgruppen nicht löschen, damit der Bedienungskomfort auch gegenüber neueren IAM-Benutzern gewahrt bleibt.

Nach der Migration Ihrer Berechtigungen der klassischen Infrastruktur dürfen Sie diese Berechtigungen nicht mehr verwenden. In der folgenden Tabelle sind alle migrierten Berechtigungen für die klassische Infrastruktur aufgeführt, die nun Teil von IAM-Zugriffsgruppen sind.
{: important}

| Name der Zugriffsgruppe für migrierte Berechtigungen | Zulässige Aktionen |
|----------|---------|
| Kontozusammenfassung anzeigen | Kontozusammenfassungsseite, Rechnungen und Zahlungen anzeigen. |
| Compliance-Bericht abrufen | Compliance-Berichte anfordern. |
| Unternehmensprofil bearbeiten | Unternehmensprofilinformationen bearbeiten. |
| Einmalige Zahlungen | Einmalige Zahlungen für das Benutzerkonto durchführen. |
| Zahlungsdetails aktualisieren | Informationen für wiederkehrende monatliche Zahlungen aktualisieren. |
| Einschränkung von Fällen auf die EU begrenzen | Option 'EU-Unterstützung' aktivieren oder inaktivieren, mit der die Supportfalldaten auf die Europäische Union begrenzt werden. |
| Fälle hinzufügen und Bestellungen anzeigen | Supportfälle erstellen und alle Bestellungen anzeigen  |
| Fälle bearbeiten | Beliebige Supportfälle bearbeiten. |
| Fälle durchsuchen | Alle Supportfälle durchsuchen, vorausgesetzt, die Berechtigung zum Anzeigen von Fällen ist ebenfalls zugewiesen. |
| Fälle anzeigen | Alle Supportfälle anzeigen. |
{: caption="Tabelle 1. Vordefinierte Zugriffsgruppen" caption-side="top"}

