---

copyright:

  years: 2017, 2019

lastupdated: "2019-05-16"

keywords: get started with IAM, IAM tutorial, IAM quick start

subcollection: iam

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:tip: .tip}
{:note: .note}

# Lernprogramm zur Einführung
{: #getstarted}

Dieses Lernprogramm soll Sie dabei unterstützen, sich schnell mit IBM Cloud Identity and Access Management (IAM) vertraut zu machen. Dazu werden Benutzer zu Ihrem Konto eingeladen und Sie werden diesen Benutzern Cloud IAM-Zugriffsberechtigungen zuweisen.
{:shortdesc}

Dieses Lernprogramm behandelt IAM-fähige Ressourcen. Für Services, die die Erstellung von Cloud IAM-Richtlinien zur Verwaltung des Zugriffs nicht unterstützen, können Sie [Cloud Foundry-Zugriff](/docs/iam?topic=iam-cfaccess#cfaccess) oder [Berechtigungen für die klassische Infrastruktur](/docs/iam?topic=iam-infrapermission#infrapermission) verwenden.
{: note}

## Vorbereitende Schritte
{: #iam-before-you-begin}

Wenn Sie IAM bisher nicht verwendet haben, finden Sie in der folgenden Dokumentation Informationen zu den Features, Konzepten und Komponenten des Zugriffsverwaltungssystems: 

* [IBM Cloud Identity and Access Management](/docs/iam?topic=iam-iamoverview) bietet eine kurze Übersicht über IAM in {{site.data.keyword.Bluemix_notm}}, die verfügbaren Features sowie Links zu verfügbaren Dokumenten zur Befehlszeilenschnittstelle und zur API. 
* [IAM-Konzepte](/docs/iam?topic=iam-iamconcepts) bietet eine Übersicht über die allgemeinen Konzepte in IAM, die die verschiedenen Komponenten veranschaulichen und Sie beim Einstieg unterstützen. 
* [IAM-Zugriff](/docs/iam?topic=iam-userroles) bietet eine detailliertere Beschreibung des Zugriffsmanagements mithilfe von Zugriffsrichtlinien. 


## Schritt 1. Benutzer einladen und Anfangszugriffsberechtigungen zuweisen
{: #step1}

Sie können einzelne oder auch mehrere Benutzer einladen und die Richtlinie für die Anfangszugriffsberechtigungen der eingeladenen Benutzer festlegen. Wenn Sie in einer einzigen Einladung mehrere Benutzer einladen, dann werden diesen Benutzern die gleichen Zugriffsberechtigungen zugewiesen. Auf der Seite 'Benutzer einladen' werden im Abschnitt für den Zugriff nur diejenigen Abschnitte angezeigt, zu deren Zuweisung Sie berechtigt sind.

Als Kontoeigner können Sie den von Ihnen eingeladenen Benutzern im Abschnitt 'Services' Cloud IAM-Rollen zuweisen. Sie können Zugriff auf alle Ressourcen in einer Ressourcengruppe, alle Ressourcen für einen bestimmten Service in einer Ressourcengruppe, alle Services mit aktiviertem Identity and Access Management im Konto, eine einzelne Ressource im Konto oder Kontoverwaltungsservices bereitstellen:

1. Rufen Sie **Verwalten** &gt; **Zugriff (IAM)** auf und wählen Sie dann **Benutzer** aus.
2. Klicken Sie auf **Benutzer einladen**.
3. Geben Sie die E-Mail-Adresse der Benutzer an, die eingeladen werden sollen.
4. Erweitern Sie im Abschnitt **Zugriff** die Ansicht der Option **Services**.
5. Wählen Sie diese Option aus, um Zugriff auf eine **Ressource**, auf Ressourcen innerhalb einer **Ressourcengruppe** oder auf **Kontoverwaltungsservices** zu erteilen.
6. Gehen Sie für die von Ihnen getroffene Auswahl entsprechend den Eingabeaufforderungen vor, um den gewünschten Zugriff anzugeben. Wenn Sie die Option für die Ressourcengruppe ausgewählt haben, dann können Sie dem Benutzer auch die Zugriffsberechtigungen zum Anzeigen, Bearbeiten oder Verwalten des Zugriffs auf die Ressourcengruppe erteilen, indem Sie eine Rolle für den Zugriff auf die Ressourcengruppe auswählen.
7. Wenn Sie über die erforderlichen Berechtigungen verfügen, dann können Sie in der Einladung auch Cloud Foundry-Zugriff oder Zugriff auf die Infrastruktur erteilen.
8. Klicken Sie auf **Benutzer einladen**.

Weitere Informationen finden Sie in [Benutzer einladen und Benutzern Zugriff zuweisen](/docs/iam?topic=iam-iamuserinv#iamuserinv).

## Schritt 2. Zugriffsgruppen erstellen
{: #step2}

Um die Zuweisung von Zugriff für Benutzer in Ihrem Konto zu optimieren, können Sie Zugriffsgruppen erstellen. Zugriffsgruppen bieten Ihnen die Möglichkeit, Benutzer und Service-IDs so zusammenzufassen, dass Sie ihnen dann ohne großen Aufwand Zugriff zuweisen können, indem Sie eine einzelne Richtlinie für die gesamte Gruppe definieren.

### Ihre Gruppen einrichten
{: #group_setup}

Führen Sie die folgenden Schritte aus, um eine Zugriffsgruppe zu erstellen:

1. Klicken Sie in der Menüleiste auf **Verwalten** &gt; **Zugriff (IAM)** und wählen Sie **Zugriffsgruppen** aus.
2. Klicken Sie auf **Erstellen**.
3. Geben Sie einen Namen und optional eine Beschreibung für Ihre Gruppe ein.
4. Klicken Sie auf **Erstellen**.

Fahren Sie danach mit der Einrichtung Ihrer Gruppe fort, indem Sie Benutzer oder Service-IDs hinzufügen:

1. Wählen Sie den Namen der Gruppe aus, zu der Sie diese hinzufügen wollen.
2. Klicken Sie auf **Benutzer hinzufügen**.
3. Wählen Sie die Benutzer, die Sie hinzufügen möchten, in der Liste aus und klicken Sie auf **Zu Gruppe hinzufügen**.
4. Wenn Sie Service-IDs zu der Gruppe hinzufügen wollen, klicken Sie auf **Service-IDs**.
5. Wählen Sie in der Liste die IDs aus, die Sie hinzufügen möchten, und klicken Sie auf **Zu Gruppe hinzufügen**.

### Zugriff auf Ihre Gruppen zuweisen
{: #group_access}

Nachdem Sie Ihre Gruppen erstellt haben, können Sie allen Entitäten in der Gruppe mit einer einzigen Richtlinie oder mit mehreren Richtlinien Zugriff zuweisen.

1. Klicken Sie in der Menüleiste auf **Verwalten** &gt; **Zugriff (IAM)** und wählen Sie **Zugriffsgruppen** aus.
2. Wählen Sie den Namen der Gruppe aus, für die Sie Zugriff zuweisen wollen.
3. Klicken Sie auf der Registerkarte **Zugriffsrichtlinien** auf **Zugriff zuweisen**, um eine Zugriffsrichtlinie einzurichten. Wiederholen Sie den Vorgang bei Bedarf, um weiteren Zugriff zuzuweisen.

Durch das Organisieren von Ressourcen in Ressourcengruppen und von Benutzern in Zugriffsgruppen können Sie einer Gruppe von Benutzern mit einer einzigen Richtlinie Zugriff auf eine Gruppe von Ressourcen zuweisen. Dadurch verringert sich die Gesamtzahl der Richtlinien, die Sie verwalten müssen.
{: tip}


## Schritt 3. Zugriff für vorhandene Benutzer verwalten
{: #user_access_manage}

Nachdem Sie Benutzer eingeladen, den Erstzugriff zugewiesen und Ihre Zugriffsgruppen erstellt haben, möchten Sie gegebenenfalls weiterführenden Zugriff zuweisen oder die von Ihnen zugewiesenen Erstzugriffsberechtigungen bearbeiten, um sicherzustellen, dass alle Benutzer und Gruppen in Ihrem Konto die gewünschte Zugriffsebene erhalten.

### Neue Zugriffsberechtigungen zuweisen
{: #new_access}

Führen Sie die folgenden Schritte aus, um eine neue Zugriffsrichtlinie zuzuweisen:

1. Klicken Sie in der Menüleiste auf **Verwalten** &gt; **Zugriff (IAM)** und wählen Sie **Benutzer** aus.
2. Wählen Sie den Namen des Benutzers aus, dem Sie Zugriffsberechtigungen zuweisen möchten.
3. Klicken Sie auf **Zugriffsrichtlinien**.
4. Klicken Sie auf **Zugriff zuweisen**.
5. Wählen Sie aus, wie der Zugriff zugewiesen werden soll:
    * Wählen Sie **Zugriff in einer Ressourcengruppe zuweisen** aus, um den Zugriff auf alle Ressourcen in einer Gruppe oder nur auf die Ressourcen für einen bestimmten Service in einer Gruppe zuzuweisen. Sie können dem Benutzer auch die Zugriffsberechtigungen zum Anzeigen, Bearbeiten oder Verwalten des Zugriffs auf die Ressourcengruppe erteilen, indem Sie eine Rolle für den Zugriff auf die Ressourcengruppe auswählen. Wählen Sie **Kein Zugriff** aus, wenn der Benutzer ausschließlich Zugriff auf die angegebene Ressource erhalten soll, nicht jedoch auf die Gruppe, in der sich die Ressource befindet.
    * Wählen Sie **Zugriff auf Ressourcen zuweisen** aus, um den Zugriff auf alle Ressourcen mit aktiviertem Identity and Access Management innerhalb des Kontos, alle Ressourcen eines bestimmten Service innerhalb des Kontos, auf eine einzelne Instanz oder eine einzelne Ressource innerhalb einer bestimmten Serviceinstanz zuzuweisen.
    * Wählen Sie **Zugriff auf Kontoverwaltungsservices zuweisen** aus, um Zugriff auf alle oder nur einen Kontoverwaltungsservice zu erteilen.
5. Wählen Sie eine beliebige Zusammenstellung von Rollen aus, um den Geltungsbereich der Zugriffsberechtigungen zu definieren. Weitere Informationen hierzu enthält [Cloud IAM-Rollen](/docs/iam?topic=iam-iamusermanrol#iamusermanrol).
6. Klicken Sie auf **Zuweisen**.


### Vorhandene Zugriffsberechtigungen bearbeiten
{: #editing_access}

Sie können die vorhandenen Zugriffsberechtigungen aktualisieren, indem Sie die zugewiesenen Rollen für einen Benutzer bearbeiten.

1. Klicken Sie in der Menüleiste auf **Verwalten** &gt; **Zugriff (IAM)** und wählen Sie **Benutzer** aus.
2. Wählen Sie den Namen des Benutzers aus, dessen Zugriffsberechtigungen bearbeitet werden sollen.
3. Klicken Sie auf **Zugriffsrichtlinien**.
4. Klicken Sie in der Zeile für die Richtlinie, die Sie bearbeiten möchten, im Menü **Aktionen** ![Symbol für Aktionsliste](../icons/action-menu-icon.svg) auf **Bearbeiten**.
4. Bearbeiten Sie die Richtlinie, indem Sie die zugewiesenen Rollen aktualisieren.
5. Klicken Sie auf **Speichern**.

Sie können die Zugriffsberechtigungen für einen Benutzer entfernen, indem Sie für die Richtlinie, die entfernt werden soll, im Menü **Aktionen** ![Symbol für Aktionsliste](../icons/action-menu-icon.svg) auf die Option **Entfernen** klicken.

## Nächste Schritte
{: #next}

Hier erfahren Sie, welche weiterführenden Schritte Sie mit Cloud IAM ausführen können, indem Sie die Informationen in der Liste der [Cloud IAM-Funktionen](/docs/iam?topic=iam-features#features) lesen.
