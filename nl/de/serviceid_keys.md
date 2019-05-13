---

copyright:

  years: 2015, 2019
lastupdated: "2019-05-01"

keywords: service ID, service ID API key, lock service ID API key, delete service ID API key

subcollection: iam

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:tip: .tip}
{:note: .note}


# API-Schlüssel für Service-IDs verwalten
{: #serviceidapikeys}

Service-IDs werden erstellt, um Anwendungen, die sowohl in als auch außerhalb von {{site.data.keyword.Bluemix_notm}} gehostet werden, den Zugriff auf Ihre {{site.data.keyword.Bluemix_notm}}-Services zu ermöglichen. API-Schlüssel werden von einer Anwendung benutzt, um sich mit einer bestimmten Service-ID zu authentifizieren und den Zugriff zu erhalten, der dieser Service-ID zugeordnet ist.
{:shortdesc}

Nach Erstellung einer Service-ID können Sie mit der Erstellung von API-Schlüsseln und der Zuweisung von Servicerichtlinien beginnen. Jede Richtlinie gibt eine bestimmte Zugriffsebene an, die zulässig ist, wenn der API-Schlüssel zur Authentifizierung bei Ihren Services verwendet wird. Weitere Informationen zur Erstellung einer Service-ID und zur Zuweisung von Richtlinien finden Sie in [Service-IDs erstellen und verwenden](/docs/iam?topic=iam-serviceids#serviceids). Detaillierte Informationen zu den CLI-Befehlen, die zur Verwaltung der API-Schlüssel von Service-IDs verwendet werden, finden Sie im Abschnitt [IAM-Zugriff, API-Schlüssel, Service-IDs und Zugriffsgruppen verwalten](/docs/cli/reference/ibmcloud?topic=cloud-cli-ibmcloud_commands_iam).

Jeder API-Schlüssel, der einer Service-ID zugeordnet wurde, übernimmt die Richtlinie, die der Service-ID zugewiesen wurde. Wenn Sie z. B. festlegen möchten, dass eine Anwendung einfach zur Anzeige von Ressourcen in einem Service berechtigt sein soll, müssen Sie einen API-Schlüssel mit einer zugeordneten Service-ID verwenden, der eine Richtlinie mit der Rolle des Anzeigeberechtigten zugewiesen ist. Wenn Sie hingegen für eine andere Anwendung festlegen möchten, dass diese über vollständigen Zugriff innerhalb eines Service verfügen soll, so müssen Sie einen API-Schlüssel verwenden, dem eine zweite Service-ID zugeordnet ist, der eine Richtlinie mit der Rolle des Administrators zugewiesen wurde.

Weitere Informationen finden Sie unter [Beispiele für die Verwendung einer Service-ID](/docs/iam?topic=iam-serviceids#examples_serviceid).

## API-Schlüssel für Service-ID erstellen
{: #create_service_key}

Erstellen Sie einen API-Schlüssel, der einer Service-ID zugeordnet werden soll.

1. Rufen Sie **Verwalten** &gt; **Zugriff (IAM)** auf und wählen Sie dann **Service-IDs** aus.
2. Wenn Sie noch keine Service-ID erstellt haben, dann erstellen Sie nun die Service-ID.
3. Klicken Sie im Menü **Aktionen** ![Symbol für Aktionsliste](../icons/action-menu-icon.svg) auf **Service-ID verwalten**.
4. Klicken Sie auf **API-Schlüssel**.
5. Klicken Sie auf **Erstellen**.
6. Fügen Sie einen Namen und eine Beschreibung hinzu, um den API-Schlüssel auf einfache Weise identifizieren zu können.
7. Klicken Sie auf **Erstellen**.
8. Speichern Sie den API-Schlüssel, indem Sie ihn kopieren oder an eine sichere Speicherposition herunterladen.

Aus Sicherheitsgründen kann der API-Schlüssel nur zum Zeitpunkt seiner Erstellung kopiert oder heruntergeladen werden. Wenn der API-Schlüssel verloren geht, müssen Sie einen neuen API-Schlüssel erstellen.
{: note}

Wenn Sie einen API-Schlüssel für eine Service-ID über die Befehlszeilenschnittstelle erstellen möchten, können Sie den Befehl [ibmcloud iam service-api-key-create](/docs/cli/reference/ibmcloud?topic=cloud-cli-ibmcloud_commands_iam#ibmcloud_iam_api_key_create) verwenden.
```
ibmcloud iam service-api-key-create NAME SERVICE_ID [-d, --description DESCRIPTION] [--file FILE] [-f, --force]
```
{: codeblock}

## API-Schlüssel für Service-ID aktualisieren
{: #update_service_key}

Sie können einen API-Schlüssel aktualisieren, indem Sie den Namen oder die Beschreibung bearbeiten, der bzw. die zur Identifikation des Schlüssels in der Benutzerschnittstelle verwendet wird.

1. Rufen Sie **Verwalten** &gt; **Zugriff (IAM)** auf und wählen Sie dann **Service-IDs** aus.
2. Klicken Sie im Menü **Aktionen** ![Symbol für Aktionsliste](../icons/action-menu-icon.svg) auf **Service-ID verwalten**.
3. Klicken Sie auf **API-Schlüssel**.
4. Klicken Sie im Menü **Aktionen** ![Symbol für Aktionsliste](../icons/action-menu-icon.svg) auf **Namen bearbeiten & Beschreibung**.

Wenn Sie einen API-Schlüssel für eine Service-ID über die Befehlszeilenschnittstelle aktualisieren möchten, können Sie den Befehl [ibmcloud iam service-api-key-update](/docs/cli/reference/ibmcloud?topic=cloud-cli-ibmcloud_commands_iam#ibmcloud_iam_api_key_update) verwenden.
```
ibmcloud iam service-api-key-update NAME SERVICE_ID  [-n, --name NEW_sNAME] [-d, --description DESCRIPTION] [-v, --version VERSION] [-f, --force]
```
{: codeblock}

## API-Schlüssel einer Service-ID sperren
{: #lockkey}

Sie können das Löschen von API-Schlüsseln, die die Identität der Service-ID darstellen, verhindern, indem Sie sie sperren. Ein gesperrter API-Schlüssel ist in der Benutzerschnittstelle durch das Symbol ![Sperrsymbol](images/locked.svg "Gesperrt") gekennzeichnet.

1. Klicken Sie in der Menüleiste auf **Verwalten** &gt; **Zugriff (IAM)** und wählen Sie **Service-IDs** aus.
2. Ermitteln Sie die Zeile für die Service-ID, für die Sie einen API-Schlüssel auswählen möchten, und wählen Sie den Namen der Service-ID aus.
3. Klicken Sie auf **API-Schlüssel**.
4. Bewegen Sie den Mauszeiger über die Zeile für den API-Schlüssel, der gesperrt werden soll, und klicken Sie auf das Menü **Aktionen** ![Symbol für Aktionsliste](../icons/action-menu-icon.svg), damit eine Liste von Optionen geöffnet wird.
5. Klicken Sie auf **API-Schlüssel sperren**.

Sie können den API-Schlüssel zu jedem beliebigen Zeitpunkt entsperren, um ihn zu aktualisieren, zu löschen oder zu entfernen oder um eine Zugriffsrichtlinie hinzuzufügen.
{: tip}

### API-Schlüssel einer Service-ID über die Befehlszeilenschnittstelle sperren bzw. entsperren
{: #lock_unlock_cli}

Verwenden Sie den folgenden Befehl, um den API-Schlüssel einer Service-ID zu sperren:

```
ibmcloud iam service-api-key-lock (APIKEY_NAME|APIKEY_UUID) (SERVICE_ID_NAME|SERVICE_ID_UUID) [-f, --force]
```

<strong>Voraussetzungen</strong>: Endpunkt, Anmeldung, Ziel

<strong>Befehlsoptionen</strong>:
<dl>
  <dt>APIKEY_NAME (erforderlich)</dt>
  <dd>Der Name des API-Schlüssels, gegenseitig ausschließend mit APIKEY_UUID</dd>
  <dt>APIKEY_UUID (erforderlich)</dt>
  <dd>Die UUID des API-Schlüssels, gegenseitig ausschließend mit APIKEY_NAME</dd>
  <dt>SERVICE_ID_NAME (erforderlich)</dt>
  <dd>Der Name der Service-ID, gegenseitig ausschließend mit SERVICE_ID_UUID</dd>
  <dt>SERVICE_ID_UUID (erforderlich)</dt>
  <dd>Die UUID der Service-ID, gegenseitig ausschließend mit SERVICE_ID_NAME</dd>
  <dt>-f, --force</dt>
  <dd>Sperren ohne Bestätigung</dd>
</dl>

<strong>Beispiele</strong>:

Service-API-Schlüssel `sample-key` der Service-ID `sample-service` sperren:

```
ibmcloud iam service-api-key-lock sample-key sample-service
```

Verwenden Sie den folgenden Befehl, um den API-Schlüssel einer Service-ID zu entsperren:

```
ibmcloud iam service-api-key-unlock (APIKEY_NAME|APIKEY_UUID) (SERVICE_ID_NAME|SERVICE_ID_UUID) [-f, --force]
```


## API-Schlüssel für Service-ID löschen
{: #delete_service_key}

Sie können einen API-Schlüssel löschen, der einer Service-ID zugeordnet ist. Allerdings wird durch das Löschen eines momentan durch eine Anwendung benutzten API-Schlüssels dieser Anwendung die Möglichkeit entzogen, sich bei Ihren Services zu authentifizieren.

1. Rufen Sie **Verwalten** &gt; **Zugriff (IAM)** auf und wählen Sie dann **Service-IDs** aus.
2. Wenn Sie noch keine Service-ID erstellt haben, dann erstellen Sie nun die Service-ID.
3. Klicken Sie im Menü **Aktionen** ![Symbol für Aktionsliste](../icons/action-menu-icon.svg) auf **Service-ID verwalten**.
4. Klicken Sie auf **API-Schlüssel**.
5. Klicken Sie im Menü **Aktionen** ![Symbol für Aktionsliste](../icons/action-menu-icon.svg) auf **Löschen**.

Wenn Sie einen API-Schlüssel für eine Service-ID über die Befehlszeilenschnittstelle löschen möchten, können Sie den Befehl [ibmcloud iam service-api-key-delete](/docs/cli/reference/ibmcloud?topic=cloud-cli-ibmcloud_commands_iam#ibmcloud_iam_api_key_delete) verwenden.
```
ibmcloud iam service-api-key-delete NAME SERVICE_ID [-f, --force]
```
{: codeblock}
