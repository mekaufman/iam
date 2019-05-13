---

copyright:

  years: 2015, 2019
lastupdated: "2019-05-01"

keywords: service ID, service ID access, managing access for service IDs

subcollection: iam

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:tip: .tip}
{:note: .note}

# Zugriffsrichtlinien für Service-IDs verwalten
{: #serviceidpolicy}

Wenn Sie eine Service-ID erstellen, so können Sie dieser Service-ID Servicerichtlinien zuweisen, um zu steuern, welche Zugriffsebene zulässig ist, wenn die Service-ID zur Authentifizierung bei Ihren Services verwendet wird. Sie können diese zugewiesenen Zugriffsrichtlinien jederzeit aktualisieren, indem Sie eine vorhandene Richtlinie ändern, eine Richtlinie löschen oder eine neue Richtlinie zuweisen.
{:shortdesc}

Wenn Sie eine vorhandene Richtlinie für eine momentan verwendete Service-ID löschen oder bearbeiten, kann es zu Serviceunterbrechungen kommen.
{: note}

## Neue Zugriffsberechtigungen zuweisen
{: #access_new}

Um Zugriffsberechtigungen für alle Ressourcen einer Ressourcengruppe oder für einen einzelnen Service in einer Ressourcengruppe zuzuweisen, müssen Sie die folgenden Schritte ausführen:

1. Klicken Sie in der Menüleiste auf **Verwalten** &gt; **Zugriff (IAM)** und wählen Sie **Service-IDs** aus.
2. Wählen Sie die Service-ID, der Sie eine Servicerichtlinie zuweisen wollen, in der Tabelle aus.
3. Klicken Sie auf **Zugriffsrichtlinien**.
4. Klicken Sie auf **Zugriff zuweisen**.
5. Wählen Sie die Option für die **Zuweisung nach Ressourcengruppe** aus.
6. Wählen Sie eine Ressourcengruppe aus.
7. Wählen Sie eine Rolle für das Feld **Zugriff für eine Ressourcengruppe zuweisen** aus. Diese Option ermöglicht dem Benutzer, die Ressourcengruppe in seiner Ressourcenliste anzuzeigen, den Ressourcengruppennamen zu bearbeiten oder den Benutzerzugriff auf die Gruppe zu verwalten. Sie können **Kein Zugriff** auswählen, wenn der Benutzer ausschließlich Zugriff auf die Ressource erhalten soll, die Sie angeben, nicht jedoch auf die Gruppe, der die Ressource zugewiesen ist.
8. Wählen Sie einen Service in der Ressourcengruppe aus, oder wählen Sie aus, dass der Zugriff auf alle Services in der ausgewählten Gruppe bereitgestellt werden soll.
9. Wählen Sie eine beliebige Zusammenstellung von Rollen aus, um dem Benutzer die gewünschten Zugriffsberechtigungen zuzuweisen. Dieser Zugriff gilt nur für die Ressourcen, die Sie für die Richtlinie ausgewählt haben. Der Zugriff auf den Container selbst, der die Ressourcengruppe darstellt, wird hingegen nicht erteilt.
10. Wählen Sie **Zuweisen** aus.

Führen Sie die folgenden Schritte aus, um die Zugriffsberechtigungen für eine einzelne Ressource im Konto zuzuweisen:

1. Klicken Sie in der Menüleiste auf **Verwalten** &gt; **Zugriff (IAM)** und wählen Sie **Service-IDs** aus.
2. Wählen Sie die Service-ID, der Sie eine Servicerichtlinie zuweisen wollen, in der Tabelle aus.
3. Klicken Sie auf **Zugriffsrichtlinien**.
4. Klicken Sie auf **Zugriff zuweisen**.
5. Wählen Sie die Option für die **Zuweisung nach Ressource** aus.
6. Wählen Sie einen Service aus.
7. Wählen Sie **Alle aktuellen Regionen** oder eine bestimmte Region aus, wenn Sie vom System dazu aufgefordert werden.
8. Wählen Sie **Alle aktuellen Serviceinstanzen** oder eine bestimmte Serviceinstanz aus.
9. Abhängig vom ausgewählten Service können die folgenden Felder angezeigt werden. Wenn Sie für diese Felder keine Werte eingeben, wird die Richtlinie nicht auf der Bucketebene, sondern auf der Serviceinstanzebene zugewiesen.
    * **Ressourcentyp**: Geben Sie **Bucket** ein.
    * **Ressourcen-ID**: Geben Sie den Namen des Buckets ein.
10. Wählen Sie eine beliebige Zusammenstellung von Rollen aus, um dem Benutzer die gewünschten Zugriffsberechtigungen zuzuweisen.
11. Wählen Sie **Zuweisen** aus.

Führen Sie die folgenden Schritte aus, um Zugriff auf einen einzelnen Kontoverwaltungsservice oder alle Kontoverwaltungsservices zu erteilen:

1. Klicken Sie in der Menüleiste auf **Verwalten** &gt; **Zugriff (IAM)** und wählen Sie anschließend **Service-IDs** aus.
2. Wählen Sie die Service-ID, der Sie eine Servicerichtlinie zuweisen wollen, in der Tabelle aus.
3. Klicken Sie auf **Zugriffsrichtlinien**.
4. Klicken Sie auf **Zugriff zuweisen**.
5. Wählen Sie diese Option aus, um Zugriff auf **Kontoverwaltungsservices** zu erteilen.
6. Wählen Sie **Alle Kontoverwaltungsservices** oder einen bestimmten Kontoverwaltungsservice aus.
7. Wählen Sie eine beliebige Zusammenstellung von Rollen aus, um die gewünschten Zugriffsberechtigungen zuzuweisen.

Möglicherweise erhalten Sie eine Nachricht mit dem Inhalt, dass für die von Ihnen ausgewählten Details bereits eine Richtlinie vorhanden ist. Wenn eine Richtlinie mit exakt diesen Details und Rollen erstellt wird, werden Sie aufgefordert, die neue Richtlinie zu ändern, da Richtlinien nicht doppelt vorhanden sein dürfen. Wenn Sie eine Richtlinie mit den gleichen Details jedoch mit anderen Rollenzuweisungen als in einer vorhandenen Richtlinie erstellen, werden Sie aufgefordert, die vorhandene Richtlinie zu überprüfen und sie mit Rollenzuweisungen zu aktualisieren, die Sie zuweisen möchten.
{: tip}

## Vorhandene Zugriffsberechtigungen bearbeiten
{: #access_edit}

Gehen Sie wie folgt vor, um eine vorhandene Richtlinie zu bearbeiten:

1. Klicken Sie in der Menüleiste auf **Verwalten** &gt; **Zugriff (IAM)** und wählen Sie **Service-IDs** aus.
2. Wählen Sie die Service-ID, für die eine Servicerichtlinie bearbeitet werden soll, in der Tabelle aus.
3. Klicken Sie auf **Zugriffsrichtlinien**.
4. Ermitteln Sie die Zeile für die Richtlinie, die bearbeitet werden soll, und wählen Sie im Menü **Aktionen** ![Symbol für Aktionsliste](../icons/action-menu-icon.svg) die Option **Richtlinie bearbeiten** aus.
5. Nehmen Sie die gewünschten Änderungen vor und speichern Sie dann die Richtlinie.

Wenn Sie eine Servicerichtlinie über die Befehlszeilenschnittstelle (CLI) aktualisieren möchten, können Sie den Befehl [ibmcloud iam service-policy-update](/docs/cli/reference/ibmcloud?topic=cloud-cli-ibmcloud_commands_iam#ibmcloud_iam_service_policy_update) verwenden.
```
ibmcloud iam service-policy-update SERVICE_ID POLICY_ID [-v, --version VERSION] {--file JSON_FILE | [-r, --roles ROLE_NAME1,ROLE_NAME2...] [--service-name SERVICE_NAME] [--service-instance SERVICE_INSTANCE] [--region REGION] [--resource-type RESOURCE_TYPE] [--resource RESOURCE] [--resource-group-name RESOURCE_GROUP_NAME] [--resource-group-id RESOURCE_GROUP_ID]} [-f, --force]",
```
{: codeblock}

Bei der Bearbeitung des Zugriffs für eine Service-ID erhalten Sie möglicherweise eine Nachricht mit dem Inhalt, dass Richtlinien nicht doppelt vorhanden sein dürfen. Wenn Sie eine vorhandene Richtlinie bearbeiten und die von Ihnen vorgenommenen Änderungen in Konflikt mit bereits zugewiesenen Zugriffsberechtigungen stehen, können Sie auswählen, ob Sie die Richtlinie, die Sie gerade bearbeiten, so ändern möchten, dass sie anderen Zugriff zur Verfügung stellt, oder ob Sie zu der bereits vorhandenen Richtlinie wechseln, mit der der Konflikt besteht, und diese überprüfen und ggf. Änderungen an ihr vornehmen wollen. Möglicherweise sollten Sie die Richtlinie, die Sie gerade bearbeiten, löschen, sofern eine andere Richtlinie vorhanden ist, die Ihren Anforderungen gerecht wird.
{: tip}

## Zugriffsberechtigungen entfernen
{: #access_remove}

Gehen Sie wie folgt vor, um eine vorhandene Richtlinie zu entfernen:

1. Klicken Sie in der Menüleiste auf **Verwalten** &gt; **Zugriff (IAM)** und wählen Sie **Service-IDs** aus.
2. Wählen Sie die Service-ID, für die eine Servicerichtlinie gelöscht werden soll, in der Tabelle aus.
3. Klicken Sie auf **Zugriffsrichtlinien**.
4. Ermitteln Sie die Zeile für die Richtlinie, die gelöscht werden soll, und wählen Sie im Menü **Aktionen** ![Symbol für Aktionsliste](../icons/action-menu-icon.svg) die Option **Entfernen** aus.
5. Überprüfen Sie die Details zu der Richtlinie, die entfernt werden soll, und klicken Sie dann zur Bestätigung des Vorgangs auf **Entfernen**.

Wenn Sie eine Servicerichtlinie über die Befehlszeilenschnittstelle (CLI) löschen möchten, können Sie den Befehl [ibmcloud iam service-policy-delete](/docs/cli/reference/ibmcloud?topic=cloud-cli-ibmcloud_commands_iam#ibmcloud_iam_service_policy_delete) verwenden.
```
ibmcloud iam service-policy-delete SERVICE_ID POLICY_ID [-f, --force]
```
{: codeblock}
