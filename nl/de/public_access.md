---

copyright:

  years: 2019

lastupdated: "2019-03-25"

keywords: public access, anonymous access

subcollection: iam

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:tip: .tip}
{:note: .note}

# Öffentlichen Zugriff auf Ressourcen ermöglichen
{: #public}

Durch den öffentlichen Zugriff auf Ressourcen können alle Benutzer und Service-IDs auf eine bestimmte Ressource in Ihrem Konto zugreifen. Dies bedeutet, dass ein Benutzer oder eine Service-ID keine Authentifizierung bei {{site.data.keyword.Bluemix}} durchführen muss, um z. B. auf Informationen in einem {{site.data.keyword.cos_full_notm}}-Bucket zuzugreifen. Nur bestimmte Services unterstützen die Möglichkeit, öffentlichen Zugriff auf bestimmte Ressourcentypen für den Service zu gewähren. Daher ist die Erstellung der entsprechenden Richtlinien nur auf Services begrenzt, die dieses Feature unterstützen.
{:shortdesc}

Wenn Sie den öffentlichen Zugriff für Ressourcen aktivieren möchten, müssen Sie die Zugriffsgruppe **Öffentlicher Zugriff** verwenden, die in Ihrem Konto zur Verfügung steht. Diese Zugriffsgruppe umfasst standardmäßig alle Benutzer und Service-IDs. Sie können die Gruppe nicht löschen oder die Zugehörigkeit zu dieser Gruppe ändern, Sie können jedoch Zugriffsrichtlinien für die Gruppe hinzufügen, bearbeiten und löschen. 

## Richtlinie für die öffentliche Zugriffsgruppe erstellen
{: #public_policy}

Führen Sie die folgenden Schritte aus, um Ihrer öffentlichen Zugriffsgruppe eine Richtlinie zuzuweisen. In der folgenden Aufgabe wird der Cloud Object Storage-Service als Beispiel für das Zuweisen des öffentlichen Zugriffs für ein Bucket mit der Bezeichnung `mybucket123` verwendet.

1. Klicken Sie in der Menüleiste auf **Verwalten** &gt; **Zugriff (IAM)** und wählen Sie **Zugriffsgruppen** aus.
2. Wählen Sie die Gruppe **Öffentlicher Zugriff** aus. 
3. Klicken Sie auf **Zugriff zuweisen**.
4. Wählen Sie **Cloud Object Storage** in der Serviceliste aus. 
5. Geben Sie `bucket` als Ressourcentyp ein. 
6. Geben Sie `mybucket123` als Ressourcen-ID ein. 
7. Klicken Sie auf **Zuweisen**.
8. Klicken Sie auf **Ja**, um zu bestätigen, dass Sie der Ressource die Richtlinie für den öffentlichen Zugriff zuweisen möchten, und klicken Sie dann auf **Zuweisen**.
