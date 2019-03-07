---

copyright:

  years: 2018, 2019
lastupdated: "2019-01-28"

keywords: advantage of access groups, access assignment process, assign access, best practice, access management, strategy

subcollection: iam

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:tip: .tip}

# Bewährte Verfahren für die Zuweisung von Zugriff
{: #account_setup}

Sie können den Prozess der Zugriffszuweisung optimieren, wenn Sie sich Zugriffsgruppen zunutze machen, um die geringstmögliche Anzahl von Richtlinien zuzuweisen, indem Sie allen Benutzern und Service-IDs, die zu derselben Zugriffsgruppe gehören, denselben Zugriff erteilen. Verwenden Sie die Informationen zu den vorliegenden bewährten Verfahren, um mehr dazu zu erfahren, wie Sie Benutzern Zugriff auf Ressourcen, Ressourcengruppen und Kontoverwaltungsservices bereitstellen.
{:shortdesc}

Um sicherzustellen, dass Ihr Konto optimal eingerichtet ist, prüfen Sie die Informationen in [Bewährte Verfahren für das Einrichten Ihres Kontos](/docs/account?topic=account-account_setup#account_setup) und [Bewährte Verfahren für die Organisation von Ressourcen in Ressourcengruppen](/docs/resources?topic=resources-bp_resourcegroups#bp_resourcegroups).
{: tip}

## Was ist eine gute Strategie für Zugriffsgruppen?
{: #rg_strategy}

Eine Zugriffsgruppe ist eine Gruppierung von Benutzern und Service-IDs, der derselbe IAM-Zugriff erteilt werden kann. Sie können der Gruppe eine einzige Richtlinie zuweisen, anstatt denselben Zugriff mehrmals für den einzelnen Benutzer oder die einzelne Service-ID zuzuweisen.

Vorausgesetzt, dass Sie die Informationen in [Bewährte Verfahren für das Einrichten Ihres Kontos](/docs/account?topic=account-account_setup#account_setup) umgesetzt haben, wäre es zum Zuweisen von Zugriff logisch, pro gewünschter Zugriffsebene eine Zugriffsgruppe zu erstellen. Danach können Sie jede Zugriffsgruppe den zuvor erstellten Ressourcengruppen zuordnen. Falls Sie zum Beispiel den Zugriff auf das Projekt `CustApp` steuern möchten, könnten Sie die folgenden Zugriffsgruppen erstellen:

* Auditor-Group (Auditorgruppe)
* Developer-Group (Entwicklergruppe)
* Admin-Group (Administratorgruppe)

Ordnen Sie für die Gruppe 'Auditor-Group' zwei Zugriffsrichtlinien zu, die den Ressourcengruppen `CustApp-Test` und `CustApp-Prod` die Anzeigeberechtigung erteilen. Ordnen Sie für die Gruppe 'Developer-Group' zwei Zugriffsrichtlinien zu, die den Umgebungen `CustApp-Dev` und `CustApp-Test` den Editorzugriff erteilen. Ordnen Sie für die Gruppe 'Admin-Group' drei Zugriffsrichtlinien zu, die allen drei `CustApp`-Ressourcengruppen den Administratorzugriff erteilen.

Obwohl diese Vorschläge für ein hypothetisches Szenario konzipiert sind, können Sie die Zuordnung zwischen Zugriffs- und Ressourcengruppen nach Gutdünken konfigurieren.

## Zugriffsgruppen erstellen
{: #access-group-setup}

Führen Sie die folgenden Schritte aus, um eine Zugriffsgruppe zu erstellen:

1. Klicken Sie in der {{site.data.keyword.Bluemix}}-Konsole auf **Verwalten** &gt; **Zugriff (IAM)** und wählen Sie **Zugriffsgruppen** aus.
2. Klicken Sie auf **Erstellen**.
3. Geben Sie einen Namen und eine Beschreibung für die Gruppe ein.
4. Klicken Sie auf **Erstellen**.

Nachdem Sie eine Zugriffsgruppe erstellt haben, können Sie Benutzer und Service-IDs zu ihr hinzufügen.

## Wie IAM-Zugriffsrichtlinien Zugriff bereitstellen
{: #how_access}

Eine Richtlinie setzt sich aus einem Subjekt, einem Ziel und einer Rolle zusammen. Das Subjekt ist in diesem Fall die Zugriffsgruppe. Das Ziel ist das, auf das das Subjekt Zugriff haben soll, wie beispielsweise eine Gruppe von Ressourcen, eine Serviceinstanz, alle Services im Konto oder alle Instanzen eines Service. Die Rolle definiert, welchen Grad von Zugriff ein Benutzer erhält.

Die am häufigsten verwendeten Rollen sind 'Viewer' (Anzeigeberechtigter), 'Editor' (Bearbeiter) und 'Administrator' (Administrator). Die Rolle des Anzeigeberechtigten ('Viewer') bietet den geringsten Zugriff und beschränkt sich auf das Anzeigen von Instanzen und Ressourcengruppen in einem Konto. Die Rolle des Bearbeiters verfügt über mehr Zugriff und ermöglicht das Erstellen, Bearbeiten, Löschen und Binden von Serviceinstanzen. Die Rolle des Administrators gewährt Zugriff auf alle Aktionen, die zum Arbeiten mit einer Serviceinstanz erforderlich sind, und ist außerdem in der Lage, anderen Zugriff zuzuweisen. Es gibt jedoch zwei unterschiedliche Kategorien von Rollen, die Sie berücksichtigen sollten: Plattformrollen und Servicerollen. Weitere Informationen zu den Rollen, die zugewiesen werden können, finden Sie in [Cloud IAM-Rollen](/docs/iam?topic=iam-iamusermanrol#iamusermanrol).

## Zugriff auf Zugriffsgruppen zuweisen
{: #assigning-access}

Sie können Ressourcen in einer Ressourcengruppe und Benutzer sowie Service-IDs in einer Zugriffsgruppe zusammenfassen, um die Zuweisung von Zugriff so einfach wie möglich zu gestalten. Nachdem Sie die einzelnen Gruppen eingerichtet haben, können Sie Zugriffsrichtlinien für die einzelnen Zugriffsgruppen erstellen, um den Benutzern in Ihrem Konto Zugriff auf die erstellten Ressourcen zu erteilen.

1. Klicken Sie auf **Verwalten** &gt; **Zugriff (IAM)** und wählen Sie **Zugriffsgruppen** aus.
2. Wählen Sie den Namen der Zugriffsgruppe aus, für die Sie Zugriff zuweisen wollen.
3. Wählen Sie die Registerkarte **Zugriffsrichtlinien** aus und klicken Sie dann auf **Zugriff zuweisen**. Zum Zuweisen von Zugriff stehen Ihnen die folgenden Optionen zur Verfügung:

  * **Zugriff auf Ressourcen in einer Ressourcengruppe zuweisen**: Verwenden Sie diese Option, um die zweiteilige Richtlinie anzugeben, die für Benutzer benötigt wird, die Ressourcen aus dem Katalog erstellen und diese Ressourcen einer Ressourcengruppe zuweisen. Wenn Sie diese Option verwenden, können Sie Zugriff auf die Ressourcengruppe selbst und auf alle Ressourcen in einer bestimmten Ressourcengruppe oder auf nur einen Service oder eine Instanz in der Ressourcengruppe erteilen.
  * **Zugriff auf Ressourcen zuweisen**: Verwenden Sie diese Option, um allen IAM-fähigen Services im gesamten Konto oder einem einzelnen Service im Konto Zugriff zuzuweisen, nicht aber einer Instanzebene.
  * **Zugriff auf Kontoverwaltungsservices zuweisen**: Verwenden Sie diese Option, um zum Delegieren einiger Ihrer Funktionen als Kontoeigner einem Benutzer Zugriff auf Kontoverwaltungsservices zu erteilen. So können Sie z. B. die Fähigkeit delegieren, Abrechnung und Nutzung einzusehen, Benutzer einzuladen und zu entfernen, Zugriffsgruppen zu verwalten, Katalogservices zu verwalten oder Service-IDs zu verwalten. Sie können Zugriff auf alle Kontoverwaltungsservices oder nur auf einen einzigen bereitstellen.

Sie können mehreren Benutzern ganz einfach Administratorzugriff auf den gesamten Inhalt eines Kontos erteilen, indem Sie eine Zugriffsgruppe erteilen und dieser dann zwei Richtlinien zuweisen. Erstellen Sie die erste Richtlinie unter Verwendung der Option **Zugriff auf Ressourcen zuweisen** und wählen Sie bei zugewiesener Administratorrolle die Option **Alle Services mit aktiviertem Identity and Access Management** aus. Erstellen Sie die zweite Richtlinie mit der Option **Zugriff auf Kontoverwaltungsservices zuweisen** und wählen Sie bei zugewiesener Administratorrolle die Option **Alle Kontoverwaltungsservices** aus.
{: tip}
