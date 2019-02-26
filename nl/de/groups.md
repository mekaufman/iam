---

copyright:

  years: 2018, 2019
lastupdated: "2019-01-30"

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:tip: .tip}
{:note: .note}


# Zugriffsgruppen einrichten
{: #groups}

Eine Zugriffsgruppe kann erstellt werden, um eine Gruppe von Benutzern und Service-IDs in einer einzigen Entität zu organisieren, die es Ihnen leicht macht, Zugriff zuzuweisen. Sie können der Gruppe eine einzige Richtlinie zuweisen, anstatt denselben Zugriff mehrmals für den einzelnen Benutzer oder die einzelne Service-ID zuzuweisen.
{:shortdesc}

Um neue Zugriffsgruppen zu verwalten oder zu erstellen, müssen Sie der Kontoeigner, Administrator oder Editor (Bearbeiter) für den IAM-Zugriffsgruppenservice im Konto oder der zugeordnete Administrator oder Editor (Bearbeiter) für 'Alle Kontoverwaltungsservices' sein. Darüber hinaus kann ein Administrator oder Bearbeiter für die Verwaltung einer einzelnen Gruppe zugewiesen werden, indem eine Zugriffsrichtlinie erstellt wird, deren Ressource die Zugriffsgruppen-ID ist. Weitere Informationen über Zugriffsrichtlinien und Rollen für den IAM-Zugriffsgruppenservice finden Sie im Abschnitt zum [IAM-Zugriff](/docs/iam?topic=iam-userroles#userroles).

Um die Zuweisung und Verwaltung des Zugriffs noch einfacher zu gestalten, können Sie Ressourcengruppen einrichten, um eine Gruppe von Ressourcen zu organisieren, auf die eine Gruppe von Benutzern Zugriff haben soll. Wenn Ihre Ressourcengruppe eingerichtet ist, können Sie eine Richtlinie zuordnen, die den Zugriff auf alle Ressourcen in dieser Gruppe ermöglicht, anstatt Zugriffsrichtlinien für einzelne Serviceinstanzen innerhalb Ihres Kontos zu erstellen. 
{: tip}

## Zugriffsgruppe erstellen
{: #create_ag}

Führen Sie die folgenden Schritte aus, um eine Zugriffsgruppe zu erstellen:

1. Klicken Sie in der Menüleiste auf **Verwalten** &gt; **Zugriff (IAM)** und wählen Sie **Zugriffsgruppen** aus.
2. Klicken Sie auf **Erstellen**.
3. Geben Sie einen Namen und eine optionale Beschreibung für Ihre Gruppe ein und klicken Sie auf **Erstellen**.

Fahren Sie danach mit der Einrichtung Ihrer Gruppe fort, indem Sie Benutzer oder Service-IDs hinzufügen:

1. Wählen Sie den Namen der Gruppe aus, zu der Sie diese hinzufügen wollen.
2. Klicken Sie auf der Registerkarte **Benutzer** auf **Benutzer hinzufügen**. 
3. Wählen Sie die Benutzer, die Sie hinzufügen möchten, in der Liste aus und klicken Sie auf **Zu Gruppe hinzufügen**.
4. Wenn Sie Service-IDs zu der Gruppe hinzufügen wollen, klicken Sie auf **Service-IDs** und anschließend auf **Service-ID hinzufügen**.
5. Wählen Sie die IDs, die Sie hinzufügen möchten, in der Liste aus und klicken Sie auf **Zu Gruppe hinzufügen**.

Sie können eine Gruppe löschen, indem Sie die Option **Gruppe entfernen** auswählen. Durch das Entfernen einer Gruppe aus dem Konto entfernen Sie alle Benutzer und Service-IDs aus der Gruppe sowie den gesamten der Gruppe zugewiesenen Zugriff.
{: note}

Wenn Sie eine Zugriffsgruppe über die Befehlszeilenschnittstelle (CLI) erstellen möchten, können Sie den Befehl [ibmcloud iam access-group-create](/docs/cli/reference/ibmcloud?topic=cloud-cli-ibmcloud_commands_iam#ibmcloud_iam_access_group_create) verwenden.
```
ibmcloud iam access-group-create GROUP_NAME [-d, --description DESCRIPTION]
```
{: codeblock}


## Zugriff auf eine Gruppe zuweisen
{: #access_ag}

Nachdem Sie Ihre Gruppe mit Benutzern und Service-IDs eingerichtet haben, können Sie der Gruppe eine gemeinsame Zugriffsrichtlinie zuweisen. Denken Sie daran, dass alle Richtlinien, die Sie für die Gruppe festlegen, für alle Entitäten in der Gruppe gelten.

1. Klicken Sie in der Menüleiste auf **Verwalten** &gt; **Zugriff (IAM)** und wählen Sie **Zugriffsgruppen** aus.
2. Wählen Sie den Namen der Gruppe aus, auf die Sie Zugriff zuweisen wollen. 
3. Klicken Sie auf **Zugriffsrichtlinien**.
4. Klicken Sie auf **Zugriff zuweisen**. 
5. Wählen Sie die Zuweisung von Zugriff nach Ressourcen in einer Ressourcengruppe, nach einzelnen im Konto verfügbaren Ressourcen oder nach Kontoverwaltungsservices aus.

Wenn Sie eine Zugriffsgruppenrichtlinie über die Befehlszeilenschnittstelle (CLI) erstellen möchten, können Sie den Befehl [ibmcloud iam access-group-policy-create](/docs/cli/reference/ibmcloud?topic=cloud-cli-ibmcloud_commands_iam#ibmcloud_iam_access_group_policy_create) verwenden.
```
ibmcloud iam access-group-policy-create GROUP_NAME {-f, --file @JSON_FILE | --roles ROLE_NAME1,ROLE_NAME2... [--service-name SERVICE_NAME] [--service-instance SERVICE_INSTANCE] [--region REGION] [--resource-type RESOURCE_TYPE] [--resource RESOURCE] [--resource-group-name RESOURCE_GROUP_NAME] [--resource-group-id RESOURCE_GROUP_ID]}
```
{: codeblock}


