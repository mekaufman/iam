---

copyright:

  years: 2017, 2019

lastupdated: "2019-02-21"

keywords: service ID, create service ID, lock service ID, service ID example

subcollection: iam

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:tip: .tip}
{:note: .note}

# Service-IDs erstellen und verwenden
{: #serviceids}

Eine Service-ID dient (ähnlich wie eine Benutzer-ID, die einen Benutzer identifiziert) zur Identifikation eines Service oder einer Anwendung. Eine von Ihnen erstellte Service-ID kann verwendet werden, um einer Anwendung außerhalb von {{site.data.keyword.Bluemix_notm}} den Zugriff auf Ihre {{site.data.keyword.Bluemix_notm}}-Services zu erteilen. Sie können der Service-ID spezielle Zugriffsrichtlinien zuweisen, die die Berechtigungen zur Verwendung bestimmter Services einschränken, oder auch die Berechtigungen für den Zugriff auf unterschiedliche Services kombinieren. Da Service-IDs nicht an bestimmte Benutzer gebunden sind, bleibt die Service-ID bestehen, wenn der zugehörige Benutzer Ihre Organisation verlässt und sein Konto deshalb gelöscht wird. Auf diese Weise wird sichergestellt, dass Ihre Anwendung oder Ihr Service weiterhin funktionsbereit bleibt.
{:shortdesc}

Bei der Erstellung einer Service-ID werden ein eindeutiger Name und eine eindeutige Beschreibung erstellt, die Sie einfach identifizieren und mit der Sie in der Benutzerschnittstelle problemlos arbeiten können. Nach der Erstellung Ihrer Service-ID können Sie API-Schlüssel speziell für die einzelnen Service-IDs erstellen, die von Ihrer Anwendung benutzt werden können, um die Authentifizierung bei Ihren {{site.data.keyword.Bluemix_notm}}-Services durchzuführen. Um sicherzustellen, dass Ihre Anwendung über die korrekten Zugriffsberechtigungen für die Authentifizierung bei Ihren {{site.data.keyword.Bluemix_notm}}-Services verfügt, können Sie die Zugriffsrichtlinien verwenden, die den von Ihnen erstellten Service-IDs zugewiesen werden.

Die Zugriffsrichtlinien, die einer Service-ID zugeordnet sind, ermöglichen bestimmte Aktionen, die ausgeführt werden können, wenn diese Service-ID für den Zugriff auf einen bestimmten Service verwendet wird. Einer einzelnen Service-ID können mehrere Richtlinien zugewiesen sein, die definieren, welche Zugriffsebene für den Zugriff auf mehrere Services mit aktiviertem Identity and Access Management oder sogar auf verschiedene Instanzen eines einzigen Service zulässig ist. Nehmen Sie als Beispiel an, dass Sie über zwei Services mit jeweils zwei Serviceinstanzen verfügen. Sie könnten nun allen verfügbaren Instanzen des einen Service die Rolle des Anzeigeberechtigen und nur einer Instanz des zweiten Service die Rolle des Editors zuweisen. Auf diese Weise können Sie den Zugriff auf mehrere Services bedarfsgerecht anpassen, und zwar unter Verwendung eines einzigen API-Schlüssels für die Authentifizierung bei allen Services.


## Service-ID erstellen
{: #create_serviceid}

Führen Sie die folgenden Schritte aus, um eine Service-ID zu erstellen:

1. Rufen Sie **Verwalten** &gt; **Zugriff (IAM)** auf und wählen Sie dann **Service-IDs** aus.
2. Klicken Sie auf **Erstellen**.
3. Befolgen Sie die Vorgehensweise, um einen Namen und eine Beschreibung für Ihre Service-ID zu erstellen.
4. Klicken Sie auf **Erstellen**.

Bewegen Sie dann den Mauszeiger über die Zeile für die Service-ID, um das Menü **Aktionen** ![Symbol für Aktionsliste](../icons/action-menu-icon.svg) zum Verwalten Ihrer Service-ID zu verwenden. Als erstes können Sie eine Richtlinie zuweisen und API-Schlüssel erstellen. Weitere Informationen zum Arbeiten mit API-Schlüsseln finden Sie in [API-Schlüssel für Service-IDs verwalten](/docs/iam?topic=iam-serviceidapikeys#serviceidapikeys).

## Service-ID aktualisieren
{: #update_serviceid}

Um eine Service-ID zu aktualisieren, können Sie jederzeit ihren Namen und die Beschreibung ändern. Außerdem können Sie API-Schlüssel löschen und neue API-Schlüssel erstellen, wenn dies erforderlich ist, oder die zugewiesenen Zugriffsrichtlinien aktualisieren. Bewegen Sie den Mauszeiger über die Zeile für die Service-ID, um das Menü **Aktionen** ![Symbol für Aktionsliste](../icons/action-menu-icon.svg) zum Verwalten Ihrer Service-ID zu verwenden.

Alle Änderungen, die Sie an einer vorhandenen Service-ID durchführen, wie zum Beispiel das Ändern der zugewiesenen Richtlinien oder das Löschen eines API-Schlüssels, der gegenwärtig verwendet wird, können bei Anwendungen, die diese Service-ID verwenden, Serviceunterbrechungen verursachen.

## Service-ID sperren
{: #lock_serviceid}

Damit eine Situation vermieden werden kann, in der die Service-ID gelöscht und so ein Ausfall oder eine Unterbrechung für die Benutzer des Service verursacht wird, können Sie Service-ID über die Benutzerschnittstelle oder die Befehlszeilenschnittstelle sperren. Das Sperren einer Service-ID verhindert darüber hinaus, dass Zugriffsrichtlinien geändert, gelöscht oder zugewiesen werden. Sie können eine Service-ID nicht nur sperren, sondern auch [einzelne API-Schlüssel sperren](/docs/iam?topic=iam-lockkey#lockkey), die jeder Service-ID zugeordnet sind, die Sie in Ihrem Konto erstellen.

Gesperrte Service-IDs können zwar nicht aus dem Konto gelöscht und die Zugriffsrichtlinien können nicht aktualisiert werden, doch sie können immer noch aus jeder Zugriffsgruppe entfernt werden, zu der sie hinzugefügt wurden. Das bedeutet, dass jeder Zugriff, der einer ID durch ihre Mitgliedschaft in einer Zugriffsgruppe zugeordnet wurde, entfernt wird, wenn die Service-ID aus der Zugriffsgruppe entfernt wird.
{: note}

### Benutzerzugriff zum Sperren von Service-IDs bereitstellen
{: #access_lock_serviceid}

Damit ein Benutzer über Zugriff zum Sperren und Entsperren von Service-IDs und API-Schlüsseln verfügt, die Service-IDs zugeordnet sind, müssen sie einer bestimmten Zugriffsrichtlinie zugeordnet sein. Der notwendige Zugriff kann über zwei Arten von Zugriffsrichtlinien erteilt werden: Zugriff auf alle Service-IDs im Konto oder Zugriff auf eine bestimmte Service-ID im Konto.

Wenn Sie Zugriff auf alle Service-IDs in einem Konto zuweisen möchten, definieren Sie eine Zugriffsrichtlinie für Kontoverwaltungsservices mit den folgenden Details:

* Bearbeiter- oder Administratorrolle
* IAM Identity Service

Wenn Sie Zugriff auf eine bestimmte Service-ID in einem Konto zuordnen möchten, definieren Sie eine Zugriffsrichtlinie für Kontoverwaltungsservices mit den folgenden Details:

* Bearbeiter- oder Administratorrolle
* IAM Identity Service
* Angabe des Werts 'serviceid' im Feld für den Ressourcentyp
* Angabe der Service-ID im Feld für die Ressourcen-ID

Die können die Kennung einer bestimmten Service-ID abrufen, indem Sie **Verwalten** > **Zugriff (IAM)** aufrufen und **Service-IDs** aufrufen. Wählen Sie die Service-ID aus, zu der Sie die Details anzeigen möchten, und kopieren Sie den ID-Wert.
{: tip}

### Service-ID in Benutzerschnittstelle sperren
{: #lock_serviceid_ui}

Eine gesperrte Service-ID ist durch das Symbol ![Sperrsymbol](images/locked.svg "Gesperrt") gekennzeichnet.

1. Klicken Sie in der Menüleiste auf **Verwalten** &gt; **Zugriff (IAM)** und wählen Sie dann die Option **Service-IDs** aus.
2. Ermitteln Sie die Zeile für die Service-ID, die gesperrt werden soll, und wählen Sie im Menü **Aktionen** ![Symbol für Aktionsliste](../icons/action-menu-icon.svg) die Option **Service-ID sperren** aus.

Wählen Sie zum Entsperren einer Service-ID in der Tabelle die Service-ID aus, die Sie entsperren möchten, und wählen Sie im Menü **Aktionen** ![Symbol für Aktionsliste](../icons/action-menu-icon.svg) die Option **Service-ID entsperren** aus. Sie müssen über die erforderliche Zugriffsstufe zum Entsperren einer Service-ID verfügen.
{: tip}


### Service-ID über die Befehlszeilenschnittstelle sperren bzw. entsperren
{: #lock_serviceid_cli}

Verwenden Sie den folgenden Befehl, um eine Service-ID zu sperren:

```
ibmcloud iam service-id-lock (NAME|UUID) [-f, --force]
```

Befehlsoptionen:

<dl>
  <dt>NAME (erforderlich)</dt>
  <dd>Der Name des Service, gegenseitig ausschließend mit UUID</dd>
  <dt>UUID (erforderlich)</dt>
  <dd>Die UUID des Service, gegenseitig ausschließend mit NAME</dd>
  <dt>-f, --force</dt>
  <dd>Sperren ohne Bestätigung</dd>
</dl>

<strong>Beispiele</strong>:

Service-ID `sample-test` ohne Bestätigung sperren

```
ibmcloud iam service-id-lock sample-test -f
```

Service-ID `ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976` sperren

```
ibmcloud iam service-id-lock ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976
```

Verwenden Sie den folgenden Befehl, um eine Service-ID zu entsperren:

 ```
ibmcloud iam service-id-unlock (NAME|UUID) [-f, --force]
```

Befehlsoptionen:

<dl>
  <dt>NAME (erforderlich)</dt>
  <dd>Der Name des Service, gegenseitig ausschließend mit UUID</dd>
  <dt>UUID (erforderlich)</dt>
  <dd>Die UUID des Service, gegenseitig ausschließend mit NAME</dd>
  <dt>-f, --force</dt>
  <dd>Entsperren ohne Bestätigung</dd>
</dl>

<strong>Beispiele</strong>:

Service-ID 'sample-test' ohne Bestätigung entsperren

```
ibmcloud iam service-id-unlock sample-test -f
```

Service-ID 'ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976' entsperren

```
ibmcloud iam service-id-unlock ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976
```


## Beispiele für die Verwendung einer Service-ID
{: #examples_serviceid}

Die folgenden Beispiele zeigen, wie eine Service-ID mit den {{site.data.keyword.objectstorageshort}}- und Cloud SQL Query-Services verwendet wird.

- {{site.data.keyword.objectstorageshort}} - [Verwendung der {{site.data.keyword.Bluemix_notm}}-Befehlszeilenschnittstelle](/docs/services/cloud-object-storage?topic=cloud-object-storage-cli-ic-use-the-ibm-cli#ic-hmac-credentials).
- Cloud SQL Query - [Verwendung der SQL Query-REST-API ![Symbol für externen Link](../icons/launch-glyph.svg)](https://www.youtube.com/embed/s6S4AdJItHk?rel=0){: new_window}.
