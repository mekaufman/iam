---

copyright:

  years: 2015, 2019
lastupdated: "2019-03-05"

keywords: API key, user API keys, IBM Cloud API keys, manage user keys, create API key

subcollection: iam

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}

# API-Schlüssel für Benutzer verwalten
{: #userapikey}

Ein föderierter oder nicht föderierter Benutzer kann einen API-Schlüssel erstellen, der in der Befehlszeilenschnittstelle (Command-Line Interface, CLI) oder im Rahmen der automatisierten Anmeldung mit Ihrer Benutzeridentität verwendet werden kann. Sie können die Benutzerschnittstelle oder die Befehlszeilenschnittstelle verwenden, um Ihre API-Schlüssel zu verwalten, indem Sie Schlüssel auflisten, erstellen, aktualisieren oder löschen. Wenn Sie die {{site.data.keyword.Bluemix_notm}}-API-Schlüssel verwalten möchten, die Ihrer Benutzeridentität zugeordnet sind, rufen Sie **Verwalten** &gt; **Zugriff (IAM)** &gt; **IBM Cloud-API-Schlüssel** auf. Dann können Sie API-Schlüssel erstellen, bearbeiten oder löschen. Eine vollständige Liste der verfügbaren CLI-Befehle finden Sie im Abschnitt [`ibmcloud iam api-keys`](/docs/cli/reference/ibmcloud?topic=cloud-cli-ibmcloud_commands_iam#ibmcloud_iam_api_keys).

Als [föderierter Benutzer](/docs/account?topic=account-signup#signup) können Sie sich mit einem API-Schlüssel anmelden, indem Sie die Umgebungsvariable `IBMCLOUD_API_KEY` verwenden. Weitere Informationen zur Verwendung eines API-Schlüssels für die Anmeldung finden Sie in [Mit föderierter ID anmelden](/docs/iam?topic=iam-federated_id#federated_id).
{:shortdesc}

## API-Schlüssel erstellen
{: #create_user_key}

Als {{site.data.keyword.Bluemix_notm}}-Benutzer können Sie einen API-Schlüssel verwenden, wenn Sie ein Programm oder Script aktivieren, ohne Ihr Kennwort an das Script weiterzugeben. Ein Vorteil bei der Verwendung eines API-Schlüssels kann sein, dass ein Benutzer oder eine Organisation mehrere API-Schlüssel für verschiedene Programme erstellen kann und die API-Schlüssel können einzeln gelöscht werden, wenn diese kompromittiert wurden, ohne dass sich dies auf andere API-Schlüssel oder gar den Benutzer auswirkt. Sie können bis zu 20 API-Schlüssel erstellen.

Führen Sie die folgenden Schritte aus, um einen API-Schlüssel für Ihre Benutzeridentität in der Benutzerschnittstelle zu erstellen:

1. Rufen Sie **Verwalten** &gt; **Zugriff (IAM)** &gt; **IBM Cloud-API-Schlüssel** auf.
2. Klicken Sie auf **{{site.data.keyword.Bluemix_notm}}-API-Schlüssel erstellen**.
3. Geben Sie einen Namen und eine Beschreibung für den API-Schlüssel ein.
4. Klicken Sie auf **Erstellen**.
5. Klicken Sie dann auf **Anzeigen**, damit der API-Schlüssel angezeigt wird. Alternativ können Sie auf **Kopieren** klicken, um den Schlüssel für die spätere Verwendung zu kopieren und zu speichern, oder klicken Sie auf **Herunterladen**.

Aus Sicherheitsgründen kann der API-Schlüssel nur zum Zeitpunkt seiner Erstellung kopiert oder heruntergeladen werden. Wenn der API-Schlüssel verloren geht, müssen Sie einen neuen API-Schlüssel erstellen.
{: tip}

Verwenden Sie den folgenden Befehl, um einen API-Schlüssel über die Befehlszeilenschnittstelle zu erstellen:

1. Geben Sie `ibmcloud iam api-key-create NAME [-d DESCRIPTION] [-f, --file FILE]` in der Eingabeaufforderung ein und geben Sie einen Namen, eine Beschreibung und eine Datei zum Speichern des Schlüssels ein. Beispiel:

```
ibmcloud iam api-key-create MyKey -d "this is my API key" --file key_file
```


## API-Schlüssel aktualisieren
{: #update_user_key}

Wenn Sie den Namen oder die Beschreibung eines API-Schlüssels ändern möchten, führen Sie die folgenden Schritte in der Benutzerschnittstelle oder der Befehlszeilenschnittstelle aus.

Führen Sie die folgenden Schritte aus, um einen API-Schlüssel zu bearbeiten:

1. Rufen Sie **Verwalten** &gt; **Zugriff (IAM)** &gt; **IBM Cloud-API-Schlüssel** auf.
2. Ermitteln Sie die Zeile mit dem API-Schlüssel, den Sie aktualisieren möchten, und wählen Sie dann im Menü **Aktionen** ![Symbol für Aktionsliste](../icons/action-menu-icon.svg) die Option **Bearbeiten** aus.
3. Aktualisieren Sie die Informationen für den API-Schlüssel.
4. Klicken Sie auf **Anwenden**.

Geben Sie den folgenden Befehl ein, um einen API-Schlüssel über die Befehlszeilenschnittstelle zu bearbeiten:

1. Geben Sie `ibmcloud iam api-key-update NAME [-n NAME] [-d DESCRIPTION]` in der Eingabeaufforderung ein und geben Sie dabei den alten Namen, den neuen Namen und die neue Beschreibung für den Schlüssel an. Beispiel:

```
ibmcloud iam api-key-update MyCurrentName -n MyNewName -d "neue Beschreibung des Schlüssels"
```

## API-Schlüssel sperren
{: #lock_user_key}

Sie können das Löschen von API-Schlüsseln der Plattform, die Ihre Benutzeridentität darstellen, verhindern, indem Sie sie sperren. Ein gesperrter API-Schlüssel ist durch das Symbol ![Sperrsymbol](images/locked.svg "Gesperrt") gekennzeichnet. Das Sperren und Entsperren von API-Schlüsseln ist über die Benutzerschnittstelle oder die Befehlszeilenschnittstelle möglich.

### API-Schlüssel über die Benutzerschnittstelle sperren bzw. entsperren
{: #lockui}

1. Rufen Sie **Verwalten** &gt; **Zugriff (IAM)** &gt; **IBM Cloud-API-Schlüssel** auf.
2. Ermitteln Sie die Zeile mit dem API-Schlüssel, der gesperrt werden soll, und wählen Sie dann im Menü **Aktionen** ![Symbol für Aktionsliste](../icons/action-menu-icon.svg) die Option **Sperren** aus.

Sie können den API-Schlüssel zu jedem beliebigen Zeitpunkt entsperren, um ihn zu aktualisieren oder aus Ihrem Konto zu entfernen. Wählen Sie dazu in der Tabelle den API-Schlüssel aus, der entsperrt werden soll, und wählen Sie dann im Menü **Aktionen** ![Symbol für Aktionsliste](../icons/action-menu-icon.svg) die Option **Entsperren** aus.
{: tip}

### API-Schlüssel über die Befehlszeilenschnittstelle sperren bzw. entsperren
{: #lockcli}

Verwenden Sie den folgenden Befehl, um einen API-Schlüssel zu sperren:

```
ibmcloud iam api-key-lock (NAME|UUID) [-f, --force]
```

<strong>Voraussetzungen</strong>: Endpunkt, Anmeldung

<strong>Befehlsoptionen</strong>:
<dl>
<dt>NAME (erforderlich)</dt>
<dd>Der Name des zu sperrenden API-Schlüssels, gegenseitig ausschließend mit UUID</dd>
<dt>UUID (erforderlich)</dt>
<dd>Die UUID des zu sperrenden API-Schlüssels, gegenseitig ausschließend mit NAME</dd>
<dt>-f, --force</dt>
<dd>Sperren ohne Bestätigung erzwingen.</dd>
</dl>

<strong>Beispiel</strong>:

API-Schlüssel `test-api-key` sperren

```
ibmcloud iam api-key-lock test-api-key
```

Führen Sie den folgenden Befehl aus, um einen API-Schlüssel zu entsperren:

```
ibmcloud iam api-key-unlock (NAME|UUID) [-f, --force]
```

<strong>Voraussetzungen</strong>: Endpunkt, Anmeldung

<strong>Befehlsoptionen</strong>:
<dl>
<dt>NAME (erforderlich)</dt>
<dd>Der Name des zu entsperrenden API-Schlüssels, gegenseitig ausschließend mit UUID</dd>
<dt>UUID (erforderlich)</dt>
<dd>Die UUID des zu entsperrenden API-Schlüssels, gegenseitig ausschließend mit NAME</dd>
<dt>-f, --force</dt>
<dd>Entsperren ohne Bestätigung erzwingen.</dd>
</dl>

<strong>Beispiel</strong>:

API-Schlüssel `test-api-key` entsperren

```
ibmcloud iam api-key-unlock test-api-key
```


## API-Schlüssel löschen
{: #delete_user_key}

Wenn Sie ein Schlüsselrotationsverfahren nutzen, können Sie einen älteren Schlüssel löschen und durch einen neuen ersetzen.

Führen Sie die folgenden Schritte aus, um einen API-Schlüssel zu löschen:

1. Rufen Sie **Verwalten** &gt; **Zugriff (IAM)** &gt; **IBM Cloud-API-Schlüssel** auf.
2. Ermitteln Sie die Zeile für den API-Schlüssel, der gelöscht werden soll, und wählen Sie dann im Menü **Aktionen** ![Symbol für Aktionsliste](../icons/action-menu-icon.svg) die Option **Sperren** aus.
3. Bestätigen Sie anschließend den Löschvorgang durch Klicken auf **Löschen**.

Gehen Sie wie folgt vor, um einen API-Schlüssel über die Befehlszeilenschnittstelle zu löschen:
1. Geben Sie in der Eingabeaufforderung `ibmcloud iam api-key-delete NAME` ein und geben Sie dabei den Namen des zu löschenden Schlüssels an.
