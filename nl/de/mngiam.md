---

copyright:

  years: 2017, 2019

lastupdated: "2019-04-03"

keywords: resource access, assign access, IAM access policy, access to resource groups, edit access, remove access

subcollection: iam

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:tip: .tip}
{:note: .note}

# Zugriff auf Ressourcen verwalten
{: #iammanidaccser}

Um den Zugriff zu verwalten oder mithilfe von IAM-Richtlinien Benutzern neue Zugriffsberechtigungen zuzuweisen, müssen Sie der Kontoeigner, der Administrator für alle Services im Konto oder der zugewiesene Administrator für den entsprechenden Service oder die entsprechende Serviceinstanz sein. Weitere Informationen zu den Zugriffsrichtlinien und Rollen finden Sie im Abschnitt zum [IAM-Zugriff](/docs/iam?topic=iam-userroles#userroles).
{:shortdesc}

## Vorhandene Zugriffsberechtigungen bearbeiten
{: #edit_existing}

1. Klicken Sie in der Menüleiste auf **Verwalten** &gt; **Zugriff (IAM)** und wählen Sie **Benutzer** aus.
2. Wählen Sie den Namen des Benutzers aus, dem Sie Zugriffsberechtigungen zuweisen möchten.
3. Wählen Sie in der Zeile für die Richtlinie, die bearbeitet werden soll, das Menü **Aktionen** ![Symbol für Aktionsliste](../icons/action-menu-icon.svg) aus und klicken Sie dann auf **Richtlinie bearbeiten**.
4. Bearbeiten Sie die Richtlinie.
5. Klicken Sie auf **Speichern**.

Wenn Sie eine Benutzerrichtlinie über die Befehlszeilenschnittstelle aktualisieren möchten, können Sie den Befehl [ibmcloud iam user-policy-update](/docs/cli/reference/ibmcloud?topic=cloud-cli-ibmcloud_commands_iam#ibmcloud_iam_user_policy_update) verwenden.
```
ibmcloud iam user-policy-update USER_NAME POLICY_ID [-v, --version VERSION] {-f, --file JSON_FILE | [--roles ROLE_NAME1,ROLE_NAME2...] [--service-name SERVICE_NAME] [--service-instance SERVICE_INSTANCE] [--region REGION] [--resource-type RESOURCE_TYPE] [--resource RESOURCE] [--resource-group-name RESOURCE_GROUP_NAME] [--resource-group-id RESOURCE_GROUP_ID]}
```
{: codeblock}

Beim Bearbeiten des Zugriffs für einen Benutzer oder eine Gruppe erhalten Sie möglicherweise eine Nachricht mit dem Inhalt, dass Richtlinien nicht doppelt vorhanden sein dürfen. Wenn Sie eine vorhandene Richtlinie bearbeiten und die von Ihnen vorgenommenen Änderungen in Konflikt mit bereits zugewiesenen Zugriffsberechtigungen stehen, können Sie auswählen, ob Sie die Richtlinie, die Sie gerade bearbeiten, so ändern möchten, dass sie anderen Zugriff zur Verfügung stellt, oder ob Sie zu der bereits vorhandenen Richtlinie wechseln, mit der der Konflikt besteht, und diese überprüfen und ggf. Änderungen an ihr vornehmen wollen. Möglicherweise sollten Sie die Richtlinie, die Sie gerade bearbeiten, löschen, sofern bereits eine andere Richtlinie vorhanden ist, die Ihren Anforderungen gerecht wird.
{: note}

## Neue Zugriffsberechtigungen zuweisen
{: #assign_new_access}

Für das Zuweisen des Zugriffs auf Ressourcen stehen zwei Richtlinientypen zur Verfügung:

* Zugriff auf Ressourcen in einer Ressourcengruppe, einschließlich der Option für nur eine oder für alle Gruppen.
* Zugriff auf Ressourcen im Konto, einschließlich der Option für nur einen oder für alle Typen.

Wenn Sie einem Benutzer vollständigen Administratorzugriff für [Kontoverwaltungstasks](/docs/iam?topic=iam-account-services#account-services) wie das Einladen und Entfernen von Benutzern, die Ansicht von Abrechnung und Nutzung, die Verwaltung von Service-IDs, Zugriffsgruppen und Benutzerzugriff sowie Zugriff auf alle Kontoressourcen erteilen möchten, müssen Sie zwei Richtlinien erstellen: eine für **Alle Services mit aktiviertem Identity and Access Management** mit den Rollen Administrator und Manager und eine für **Alle Kontoverwaltungsservices** mit der Rolle Administrator.
{: tip}

### Zugriff auf Ressourcen in einer Ressourcengruppe
{: #access_to_resources}

Um Zugriffsberechtigungen für alle Ressourcen einer Ressourcengruppe oder für einen einzelnen Service in einer Ressourcengruppe zuzuweisen, müssen Sie die folgenden Schritte ausführen:

1. Klicken Sie in der Menüleiste auf **Verwalten** &gt; **Zugriff (IAM)** und wählen Sie **Benutzer** aus.
2. Wählen Sie in der Zeile für den Benutzer, dem Sie Zugriffsberechtigungen zuweisen wollen, das Menü **Aktionen** ![Symbol für Aktionsliste](../icons/action-menu-icon.svg) aus und klicken Sie dann auf **Zugriff zuweisen**.
3. Wählen Sie die Option **Zugriff in einer Ressourcengruppe zuweisen** aus.
4. Wählen Sie eine Ressourcengruppe aus.
5. Wählen Sie eine Rolle für das Feld **Zugriff für eine Ressourcengruppe zuweisen** aus, um dem Benutzer die Anzeige der Ressourcengruppe in seiner Ressourcenliste, das Bearbeiten des Ressourcengruppennamens oder das Verwalten des Benutzerzugriffs auf die Gruppe zu ermöglichen. Sie können **Kein Zugriff** auswählen, wenn der Benutzer ausschließlich Zugriff auf die Ressource erhalten soll, die Sie angeben, nicht jedoch auf die Gruppe, in der die Ressource enthalten ist.
6. Wählen Sie einen Service in der Ressourcengruppe aus, oder wählen Sie aus, dass der Zugriff auf alle Services in der ausgewählten Gruppe bereitgestellt werden soll.
7. Wählen Sie eine beliebige Zusammenstellung von Rollen aus, um dem Benutzer die gewünschten Zugriffsberechtigungen zuzuweisen. Dieser Zugriff gilt nur für die Ressourcen, die Sie für die Richtlinie ausgewählt haben. Der Zugriff auf den Container selbst, der die Ressourcengruppe darstellt, wird hingegen nicht erteilt.
8. Klicken Sie auf **Zuweisen**.

### Zugriff auf Ressourcen
{: #resourceaccess}

Führen Sie die folgenden Schritte aus, um Zugriffsberechtigungen für eine einzelne Ressource im Konto oder für alle Ressourcen im Konto zuzuweisen:

1. Klicken Sie in der Menüleiste auf **Verwalten** &gt; **Zugriff (IAM)** und wählen Sie **Benutzer** aus.
2. Wählen Sie in der Zeile für den Benutzer, dem Sie Zugriffsberechtigungen zuweisen wollen, das Menü **Aktionen** ![Symbol für Aktionsliste](../icons/action-menu-icon.svg) aus und klicken Sie dann auf **Zugriff zuweisen**.
3. Wählen Sie die Option **Zugriff auf Ressourcen zuweisen** aus.
4. Wählen Sie einen Service oder die Option **Alle Services mit aktiviertem Identity and Access Management** aus.
5. Wählen Sie **Alle aktuellen Regionen** oder eine bestimmte Region aus, wenn Sie vom System dazu aufgefordert werden.
6. Wählen Sie **Alle aktuellen Serviceinstanzen** oder eine bestimmte Serviceinstanz aus.
7. Abhängig vom ausgewählten Service können die folgenden Felder angezeigt werden. Wenn Sie für diese Felder keine Werte eingeben, wird die Richtlinie nicht auf der Bucketebene, sondern auf der Serviceinstanzebene zugewiesen.
    * **Ressourcentyp**: Geben Sie **Bucket** ein.
    * **Ressourcen-ID**: Geben Sie den Namen des Buckets ein.
8. Wählen Sie eine beliebige Zusammenstellung von Rollen aus, um dem Benutzer die gewünschten Zugriffsberechtigungen zuzuweisen.
9. Klicken Sie auf **Zuweisen**.

## Zugriffsberechtigungen entfernen
{: #removing_access}

1. Klicken Sie in der Menüleiste auf **Verwalten** &gt; **Zugriff (IAM)** und wählen Sie **Benutzer** aus.
2. Wählen Sie den Benutzernamen aus, dessen Zugriffsberechtigungen entfernt werden sollen.
3. Klicken Sie auf der Registerkarte **Zugriffsrichtlinien** in der Zeile für die Richtlinie, die entfernt werden soll, im Menü **Aktionen** ![Symbol für Aktionsliste](../icons/action-menu-icon.svg) auf **Entfernen**.  
4. Überprüfen Sie die Details zu der Benutzerrichtlinie, die entfernt werden soll, und klicken Sie dann zur Bestätigung des Vorgangs auf **Entfernen**.

Wenn Sie eine Benutzerrichtlinie über die Befehlszeilenschnittstelle entfernen möchten, können Sie den Befehl [ibmcloud iam user-policy-delete](/docs/cli/reference/ibmcloud?topic=cloud-cli-ibmcloud_iam_user_policy_delete#ibmcloud_iam_user_policy_delete) verwenden.
```
ibmcloud iam user-policy-delete USER_ID POLICY_ID [-f, --force]
```
{: codeblock}

## Zugewiesene Zugriffsberechtigungen überprüfen
{: #review_your_access}

Wenn Sie Ihre zugewiesenen Zugriffsberechtigungen in einem Konto überprüfen müssen, zu dem Sie hinzugefügt wurden, führen Sie die folgenden Schritte aus:

1. Klicken Sie in der Menüleiste auf **Verwalten** &gt; **Zugriff (IAM)** und wählen Sie **Benutzer** aus.
3. Wählen Sie Ihren Namen aus.
4. Überprüfen Sie Ihre zugewiesenen Zugriffsberechtigungen im Abschnitt **Zugriffsrichtlinien**.

Wenn Sie weiterführende Zugriffsberechtigungen benötigen, müssen Sie sich an den Kontoeigner wenden, um Ihre Zugriffsberechtigungen aktualisieren zu lassen. Alternativ hierzu können Sie sich auch an den zuständigen Administrator für den Service oder die Serviceinstanz wenden, um die Cloud IAM-Zugriffsrichtlinie aktualisieren zu lassen.
