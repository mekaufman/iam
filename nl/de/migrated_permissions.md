---

copyright:

  years: 2019

lastupdated: "2019-06-24"

keywords: migrated permissions, SoftLayer account permissions, migrated permission access group, migrated classic infrastructure permissions

subcollection: iam

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:important: .important}
{:new_window: target="_blank"}
{:note: .note}


# Migrierte SoftLayer-Kontoberechtigungen verwalten
{: #migrated_permissions}

Sie können Zugriffsgruppen für migrierte Berechtigungen verwenden, um eine Gruppe von Berechtigungen der klassischen Infrastruktur (SoftLayer) zum Verwalten von Abrechnungsinformationen und für die Arbeit mit Supportfällen zu verwalten. Zugriffsgruppen enthalten eine Gruppe von Benutzern und Service-IDs, die über denselben Zugriff verfügen. Die Benutzer in Ihrem SoftLayer-Konto, denen zuvor Konto- und Supportberechtigungen zugewiesen waren, werden nun der jeweiligen Zugriffsgruppe für die migrierte Berechtigung zugewiesen. Dies bedeutet, dass die Berechtigungen nun direkt mithilfe von IAM-Zugriffsgruppen verwaltet werden können.
{:shortdesc}

Diese speziellen Zugriffsgruppen beziehen alle entsprechenden IAM-Richtlinien ein, um das ursprüngliche Verhalten der SoftLayer-Kontoberechtigungen beizubehalten. Damit ein Benutzer beispielsweise weiterhin alle Aktualisierungen aller Benutzer für einen Supportfall anzeigen kann, umfassen die Zugriffsgruppen für migrierte Berechtigungen für die SoftLayer-Ticketing-Kontoberechtigungen eine zusätzliche IAM-Richtlinie für den Benutzerverwaltungsservice mit zugewiesener Anzeigeberechtigten-Rolle. Weitere Informationen finden Sie in [Benutzerzugriff für die Arbeit mit Supportfällen zuweisen](/docs/get-support?topic=get-support-access#access).

Nach der Migration Ihrer Berechtigungen der klassischen Infrastruktur dürfen Sie diese Berechtigungen und auch die SoftLayer-CLI oder -API zu ihrer Verwaltung nicht mehr verwenden. In der folgenden Tabelle sind die migrierten Berechtigungen für die klassische Infrastruktur aufgeführt, die nun Teil von IAM-Zugriffsgruppen sind. Zugriffsgruppen werden nur für die Berechtigungen erstellt, die bereits Benutzern zugewiesen sind. Daher bemerken Sie möglicherweise eine Untergruppe der Zugriffsgruppen, die in Ihrem Konto in der folgenden Tabelle aufgeführt sind.
{: note}

Sie können diese migrierten Berechtigungen für die klassische Infrastruktur für Benutzer direkt über IAM verwalten, indem Sie Benutzer zu den Zugriffsgruppen hinzufügen oder aus ihnen entfernen. Die Zugriffsgruppenrichtlinien sind gesperrt, um das Zugriffsverhalten für ihre Mitglieder beizubehalten. Es kann jedoch hilfreich sein, neue Zugriffsgruppen zu erstellen, die eine Kombination von Zugriffsrichtlinien für die [Kontoverwaltungsservices](/docs/iam?topic=iam-account-services#account-services) umfassen. In der folgenden Tabelle sind die Details einer IAM-Zugriffsrichtlinie aufgeführt, die die Berechtigung aus der Zugriffsgruppe für migrierte Berechtigungen enthält, sodass Sie diese Berechtigungen zusammen mit anderen in einer neuen Zugriffsgruppe erneut erstellen und auch kombinieren können.

| Name der Zugriffsgruppe für migrierte Berechtigungen | Beschreibung | Kontenverwaltungsservice | IAM-Rolle |
|-----------------------------------|-------------|-----------------------------------------|----------|
| Kontozusammenfassung anzeigen | Kontozusammenfassungsseite, Rechnungen und Zahlungen anzeigen.  |  Abrechnung |  Anzeigeberechtigter    |
| Compliance-Berichte abrufen | Compliance-Berichte anfordern. | Abrechnung |    Anzeigeberechtigter |
| Unternehmensprofil bearbeiten | Unternehmensprofilinformationen bearbeiten. | Abrechnung  | Operator |
| Zahlungsdetails aktualisieren | Informationen für wiederkehrende monatliche Zahlungen aktualisieren. | Abrechnung   | Operator |
| Einschränkung von Fällen auf die EU begrenzen | Option 'EU-Unterstützung' aktivieren oder inaktivieren, mit der die Supportfalldaten auf die Europäische Union begrenzt werden. |   Abrechnung |   Operator   |
| Fälle hinzufügen und Bestellungen anzeigen | Supportfälle erstellen und alle Bestellungen anzeigen | Support Center |   Bearbeiter   |
| Fälle bearbeiten | Beliebige Supportfälle bearbeiten. | Support Center |   Bearbeiter |
| Fälle durchsuchen | Alle Supportfälle durchsuchen, vorausgesetzt, die Berechtigung zum Anzeigen von Fällen ist ebenfalls zugewiesen. | Support Center |  Anzeigeberechtigter |
| Fälle anzeigen | Alle Supportfälle anzeigen. | Support Center und Benutzerverwaltung | Anzeigeberechtigter, Anzeigeberechtigter |
{: caption="Tabelle 1. Migrierte Infrastrukturberechtigungen, die IAM-Rollen zugeordnet sind" caption-side="top"}

Für den Zugriff auf "Fälle anzeigen" erstellen Sie zwei separate Richtlinien mit der Anzeigeberechtigten-Rolle für das Support Center und die Benutzermanagementservices. Die Richtlinie für den Benutzermanagementservice stellt sicher, dass der Benutzer alle Fälle im Konto anzeigen kann, unabhängig davon, wer sie geöffnet hat. Wenn der Kontoeigner die Möglichkeit des Benutzers, andere Benutzer im Konto anzuzeigen, eingeschränkt hat, kann ohne die Richtlinie für den Benutzermanagementservice die Anzeigemöglichkeit des Benutzers auf die Fälle beschränkt sein, die er selbst geöffnet hat.
{: note}

## Neue IAM-Zugriffsrichtlinien für migrierte Berechtigungen zuweisen
{: #migrated-permissions-iam}

Zum erneuten Erstellen der migrierten Berechtigungen, die in den einzelnen Zugriffsgruppen verfügbar sind, können Sie einzelnen Benutzern Richtlinien zuweisen oder in Ihrem Konto neue Zugriffsgruppen erstellen. Der Vorteil der Erstellung einer neuen Zugriffsgruppe besteht darin, dass Sie eine Gruppe von Berechtigungen für eine Zugriffsgruppe kombinieren können, anstatt eine Gruppe von Zugriffsgruppen mit differenziertem Geltungsbereich für die einzelnen Zugriffsgruppen zu verwalten. In diesem Beispiel wird mit den Schritten erläutert, wie eine neue Zugriffsgruppe erstellt und eine äquivalente Zugriffsrichtlinie zur Anzeige der Kontozusammenfassung und aller Supportfälle zugewiesen wird.

Bei der Neuerstellung dieser Berechtigungen durch Zuweisen neuer IAM-Zugriffsrichtlinien für die Kontoverwaltungsservices können zusätzlich zu der Einzelberechtigung, die in der Zugriffsgruppe für migrierte Berechtigungen verfügbar ist, weitere Berechtigungen einbezogen werden. Wenn Sie beispielsweise einem Benutzer die Anzeigeberechtigten-Rolle für den Abrechnungsservice zuweisen, kann dieser Benutzer mehr Aktionen ausführen, als nur die Kontozusammenfassung anzuzeigen. Eine vollständige Liste der Aktionen, die für die einzelnen Rollen zulässig sind, finden Sie im Abschnitt [Zugriff auf Kontoverwaltungsservices zuweisen](/docs/iam?topic=iam-account-services#account-services).
{: important}

Führen Sie die folgenden Schritte aus, um eine Zugriffsgruppe zu erstellen:

1. Klicken Sie in der Menüleiste auf **Verwalten** &gt; **Zugriff (IAM)** und wählen Sie **Zugriffsgruppen** aus.
2. Klicken Sie auf **Erstellen**.
3. Geben Sie einen Namen und optional eine Beschreibung für Ihre Gruppe ein und klicken Sie auf **Erstellen**.
4. Klicken Sie auf der Registerkarte **Benutzer** auf **Benutzer hinzufügen**.
3. Wählen Sie die Benutzer, die Sie hinzufügen möchten, in der Liste aus und klicken Sie auf **Zu Gruppe hinzufügen**. Sie können dieselbe Aktion über die Registerkarte **Service-IDs** ausführen, wenn Sie der Gruppe Service-IDs hinzufügen möchten.

Nachdem Sie Ihre Gruppe mit Benutzern und Service-IDs eingerichtet haben, weisen Sie ihr den Zugriff zu. Denken Sie daran, dass alle Richtlinien, die Sie für die Gruppe festlegen, für alle Mitglieder der Gruppe gelten.

1. Klicken Sie auf die Registerkarte **Zugriffsrichtlinien**.
2. Klicken Sie auf **Zugriff zuweisen**.
3. Wählen Sie die Option **Zugriff auf Kontoverwaltungsservices zuweisen** aus.
4. Wählen Sie den Service **Abrechnung** aus.
5. Wählen Sie die Rolle **Anzeigeberechtigter** aus.
6. Klicken Sie auf **Zuweisen**.
7. Klicken Sie auf **Zugriff zuweisen**, um eine zweite Zugriffsrichtlinie für die Anzeige von Supportfällen zuzuweisen.
8. Wählen Sie **Zugriff auf Kontoverwaltungsservices zuweisen** aus.
9. Wählen Sie den Service **Support Center** aus.
10. Wählen Sie die Rolle **Anzeigeberechtigter** aus.
11. Klicken Sie auf **Zuweisen**.
12. Klicken Sie auf **Zugriff zuweisen**, um eine dritte Zugriffsrichtlinie für die Anzeige von Supportfällen unabhängig von der Einstellung des Kontoeigners für die Sichtbarkeit der Kontobenutzer zuzuweisen.
13. Wählen Sie die Option **Zugriff auf Kontoverwaltungsservices zuweisen** aus.
14. Wählen Sie den Service **Benutzermanagement** aus.
15. Wählen Sie die Rolle **Anzeigeberechtigter** aus.
16. Klicken Sie auf **Zuweisen**.

Drei Richtlinien sind Ihrer Gruppe jetzt zugeordnet:

* Eine Richtlinie zum Anzeigen der Kontozusammenfassung und für alle anderen Aktionen, die der Anzeigeberechtigten-Rolle im Abrechnungsservice zugeordnet sind.
* Eine Richtlinie zum Anzeigen und Durchsuchen von Supportfällen im Konto.
* Eine Richtlinie zum Anzeigen aller Benutzer im Konto und für alle anderen Aktionen, die der Anzeigeberechtigten-Rolle im Benutzermanagementservice zugeordnet sind.

