---

copyright:

  years: 2019

lastupdated: "2019-07-24"

keywords: enterprise policy, enterprise access, assign enterprise access, enterprise service

subcollection: iam

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:tip: .tip}
{:note: .note}
{:external: target="_blank" .external}

# Unternehmenszugriff zuweisen
{: #assign-access-enterprise}

Wenn Sie einem Benutzer Zugriff für die Verwaltung eines {{site.data.keyword.Bluemix}}-Unternehmens zuweisen möchten, müssen Sie ihn für das Unternehmenskonto einladen und ihm Zugriff auf den Unternehmenskontoverwaltungsservice zuweisen.
{:shortdesc}

Der Zugriff für die Verwaltung des [Unternehmens](/docs/account?topic=account-enterprise) setzt eine Zugriffsrichtlinie innerhalb des Unternehmenskontos voraus. Wenn Sie einem Benutzer eine Richtlinie für die Unternehmenskontoverwaltung innerhalb eines untergeordneten Kontos in einem Unternehmen zuweisen, kann der Benutzer das Unternehmen, zu dem das Konto gehört, nicht verwalten. Abhängig von der zugewiesenen Rolle des Benutzers für den Unternehmenskontoverwaltungsservice im Unternehmenskonto kann der Benutzer bestimmte Aktionen durchführen:

* Neue Konten im Unternehmen erstellen
* Kontogruppen erstellen und benennen
* Konten zwischen Kontogruppen verschieben
* Vorhandene Konten in das Unternehmen importieren
* Unternehmensname oder die Domäne aktualisieren
* Nutzungsberichte für das Unternehmen, für eine bestimmte Kontogruppe und die darin enthaltenen Kontogruppen oder Konten oder für ein bestimmtes Konto anzeigen

Eine Richtlinie, die einem Benutzer den Zugriff auf den Unternehmensservice erteilt, kann entweder für das gesamte Unternehmen oder nur für eine bestimmte Kontogruppe oder ein einzelnes Konto zugewiesen werden.
{: tip}

In der Regel enthält das Unternehmenskonto selbst nicht viele Ressourcen. Stattdessen werden die Ressourcen in den untergeordneten Konten des Unternehmens erstellt. Innerhalb dieser Konten werden die Benutzer eingeladen und erhalten den erforderlichen Zugriff für das Verwalten und Nutzen der Ressourcen. Der Zugriff und die Zugehörigkeit eines Benutzers in Bezug auf das Unternehmenskonto gelten nicht für die Kontogruppen und untergeordneten Konten in der Unternehmenshierarchie. Die Benutzer- und Zugriffsverwaltung bleiben für jedes Konto isoliert, wie aus den folgenden Diagrammen hervorgeht.

Das erste Diagramm zeigt, wie Sie einem Benutzer im Unternehmenskonto eine Richtlinie zuweisen können, die zur Verwaltung des gesamten Unternehmens dient, oder eine Richtlinie, die sich auf eine Kontogruppe bezieht, die den Zugriff auf die Verwaltung nur dieser Kontogruppe sowie der anderen Kontogruppen oder untergeordneten Konten ermöglicht, die innerhalb dieser Gruppe organisiert sind.

![Unternehmenszugriff](images/enterprise-access.svg "Diagramm, das zeigt, dass die Unternehmensbenutzer nur Zugriff für die Verwaltung der Unternehmensentitäten haben")

Das Ziel und die Rolle der Richtlinie sind bei der Festlegung des Zugriffsbereichs von Bedeutung. Ein Benutzer, eine Service-ID oder eine Zugriffsgruppe in einem Unternehmen, die Gegenstand der Richtlinie sind, können Verwaltungstasks für das gesamte Unternehmen, für eine Kontogruppe, die möglicherweise andere Kontogruppen und Konten enthält, oder auch ein einzelnes Konto ausführen. Wenn Sie beispielsweise einem Benutzer im Unternehmenskonto eine Zugriffsrichtlinie für den Unternehmenskontoverwaltungsservice mit einem Ziel zuweisen, das sich auf eine bestimmte Kontogruppe bezieht, hat er den erforderlichen Zugriff zur Ausführung von Tasks in der Kontogruppe. Der Benutzer kann keine Aktionen ausführen, die das Unternehmen als Ganzes betreffen (wie z. B. das Aktualisieren des Unternehmensnamens oder der Domäne), wenn das Ziel auf eine bestimmte Kontogruppe oder ein bestimmtes Konto festgelegt ist.

Sie können Benutzern in einem untergeordneten Konto im Unternehmen Zugriffsrichtlinien zuweisen, die für die Verwaltung nur dieses Kontos oder der darin enthaltenen Ressourcen gelten. Wenn Sie einem Benutzer in einem untergeordneten Konto z. B. eine Rolle im Unternehmenskontoverwaltungsservice zuweisen, kann der Benutzer keine Aktionen auf der Ebene des Unternehmenskontos ausführen. Sie müssen sie dem Unternehmenskonto hinzufügen und die Richtlinie in diesem Kontext zuordnen.

![Kontozugriff](images/account-access.svg "Diagramm, das zeigt, dass Benutzer von untergeordneten Konten nur in ihrem Konto Zugriff haben und nicht auf das übrige Unternehmen")

## Erforderliche Richtlinien für bestimmte Jobs
{: #sample-enterprise-policies}

Abhängig von dem Job, der ausgeführt werden soll, ist möglicherweise eine Kombination aus Zugriffsrichtlinien für einen Benutzer erforderlich, der nicht der Eigner des Unternehmens ist. Die folgenden Beispiele stellen die Gruppe der Zugriffsrichtlinien bereit, die Sie einem Benutzer im Unternehmen zuweisen müssen, damit er bestimmte Tasks ausführen kann.

Wenn Sie der Eigner eines Kontos sind, das nicht Teil eines Unternehmens ist, Sie aber möchten, dass ein anderer Benutzer in Ihrem Konto in der Lage ist, Ihr Konto in ein Unternehmen umzuwandeln, können Sie diesem Benutzer die Administratorrolle für den Abrechnungskontoverwaltungsservice zuweisen.
{: note}

### Im Unternehmen die Nutzung anzeigen und die Abrechnung verwalten
{: #billing-admin-enterprise}

Damit ein Benutzer für alle Konten im Unternehmen [Nutzungsberichte anzeigen](/docs/billing-usage?topic=billing-usage-enterprise-usage), Zahlungen vornehmen und Rechnungen anzeigen kann, müssen Sie alle folgenden Zugriffsrichtlinien zuweisen:

* Rolle des Anzeigeberechtigten für Nutzungsberichte für den Unternehmenskontoverwaltungsservice im Unternehmenskonto
* Rolle des Administrators für den Abrechnungskontoverwaltungsservice im Unternehmenskonto

### Vorhandenes Konto in das Unternehmen importieren
{: #add-account}

Damit ein Benutzer [ein vorhandenes IBM Cloud-Konto in das Unternehmen importieren](/docs/account?topic=account-enterprise-add#add-accounts) kann, müssen Sie alle der folgenden Zugriffsrichtlinien zuweisen:

* Rolle des Administrators für den Abrechnungskontoverwaltungsservice in dem Konto, das importiert werden soll
* Rolle des Administrators oder Bearbeiters für den Unternehmenskontoverwaltungsservice für die Kontogruppe oder das Unternehmenskonto, der/dem das Konto hinzugefügt wird
* Rolle des Administrators für den Abrechnungskontoverwaltungsservice für das Unternehmenskonto

### Konto verschieben
{: #move-accountgroup}

Damit ein Benutzer [ein Konto in einem Unternehmen verschieben](/docs/account?topic=account-enterprise-organize#move-accounts) kann, müssen Sie die folgenden Zugriffsrichtlinien zuweisen:

* Rolle des Administrators für den Abrechnungskontoverwaltungsservice im Unternehmenskonto

Dann eine der beiden folgenden Optionen:

* Rolle des Administrators oder Bearbeiters für den Unternehmenskontoverwaltungsservice für das gesamte Unternehmen
* Rolle des Administrators oder Bearbeiters für die Ausgangs- und Zielkontogruppe, in die dieses Konto verschoben werden soll

Ausführliche Informationen zu den Aktionen, die Benutzer für jede Rolle ausführen können, finden Sie unter [Aktionen und Rollen für Kontoverwaltungsservices](/docs/iam?topic=iam-account-services#account-management-actions-roles).

## Zugriff in der Konsole zuweisen
{: #enterprise-access-console}

Führen Sie die folgenden Schritte aus, um einem vorhandenen Benutzer im Unternehmenskonto eine Zugriffsrichtlinie zuzuweisen:

Sie können das Ziel der gewünschten Richtlinie für das gesamte Unternehmen, für eine bestimmte Kontogruppe, die den Zugriff auf enthaltenen Konten beinhalten kann, oder nur für ein bestimmtes Konto in einer Kontogruppe festlegen.
{: tip}

1. Klicken Sie in der Menüleiste auf **Verwalten** &gt; **Zugriff (IAM)** und wählen Sie **Benutzer** aus.
2. Wählen Sie in der Zeile für den Benutzer, dem Sie Zugriffsberechtigungen zuweisen wollen, das Menü **Aktionen** ![Symbol für Aktionsliste](../icons/action-menu-icon.svg) aus und klicken Sie dann auf **Zugriff zuweisen**.
3. Wählen Sie diese Option aus, um Zugriff auf **Kontoverwaltungsservices** zu erteilen.
4. Wählen Sie **Unternehmen** als Service aus.
5. Optional: Legen Sie als Bereich für die Richtlinie entweder das Unternehmen, eine Kontogruppe oder das Konto fest.
6. Wählen Sie eine beliebige Zusammenstellung von Rollen aus, um die gewünschten Zugriffsberechtigungen zuzuweisen.

| Rollen | Aktionen |
|:-------|----------|
| Anzeigeberechtigter |  Unternehmen, Kontogruppen und Konten anzeigen    |
| Operator |  Unternehmen, Kontogruppen und Konten anzeigen    |
| Bearbeiter |  Unternehmen durch Bearbeiten des Namens und der Domäne anzeigen und aktualisieren, Konten und Kontogruppen erstellen, Nutzungsberichte anzeigen und Konten importieren |
| Administrator |  Unternehmen durch Bearbeiten des Namens und der Domäne anzeigen und aktualisieren, Konten und Kontogruppen erstellen, Konten zwischen Kontogruppen verschieben, bestehende Konten importieren und Nutzungsberichte anzeigen |
| Anzeigeberechtigter für Nutzungsberichte |  Unternehmen, Konten und Kontogruppen anzeigen und Nutzungsberichte für alle Konten im Unternehmen anzeigen |
{: caption="Tabelle 1. Rollen und Beispielaktionen für den Unternehmenskontoverwaltungsservice" caption-side="top"}

## Zugriff über die Befehlszeilenschnittstelle (CLI) zuweisen
{: #enterprise-cli-policy}

Um eine neue Zugriffsrichtlinie für einen Benutzer zu erstellen, führen Sie den Befehl **`ibmcloud iam user-policy-create`** aus. Im Befehlsbeispiel wird eine JSON-Datei verwendet, um die Richtliniendetails anzugeben. Im Abschnitt [Zugriff über die Anwendungsprogrammierschnittstelle (API) zuweisen](#enterprise-api-policy) finden Sie ein Beispiel für den erforderlichen Inhalt der JSON-Datei.

Benutzerrichtlinie erstellen
```
$ ibmcloud iam user-policy-create name@example.com -f policy.json
```

Weitere Informationen finden Sie unter [ibmcloud iam user-policy-create](/docs/cli/reference/ibmcloud?topic=cloud-cli-ibmcloud_commands_iam#ibmcloud_iam_user_policy_create).

## Zugriff über die Anwendungsprogrammierschnittstelle (API) zuweisen
{: #enterprise-api-policy}

Das folgende Anforderungsbeispiel weist eine Richtlinie für einen Benutzer mit der Rolle "Bearbeiter" für den Unternehmensservice in einem Unternehmenskonto mit Bezug auf eine Kontogruppe zu. Dieser Richtlinientyp ist hierarchisch und gilt für alle untergeordneten Objekte in der Hierarchie, d. h. für alle Kontogruppen oder Konten innerhalb der angegebenen Zielkontogruppe.  

```
curl -X POST \
'https://iam.cloud.ibm.com/v1/policies' \
-H 'Authorization: $TOKEN' \
-H 'Content-Type: application/json' \
-d '{
  "type": "access",
  "subjects": [
    {
      "attributes": [
        {
          "name": "iam_id",
          "value": "<IBMid-example>"
        }
      ]
    }
  ],
  "roles":[
    {
      "role_id": "crn:v1:bluemix:public:iam::::role:Editor"
    }
  ],
  "resources":[
    {
      "attributes": [
        {
          "name": "accountId",
          "value": "<account-id-example>"
        },
        {
          "name": "serviceName",
          "value": "enterprise"
        },
        {
          "name": "accountGroupId",
          "value": "<accountGroupId-example>"
        }
      ]
    }
  ]
}'
```
{: codeblock}

Weitere Informationen finden Sie unter [Richtlinie erstellen](https://cloud.ibm.com/apidocs/iam-policy-management#create-a-policy){: external}.
