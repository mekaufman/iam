---



copyright:

  years: 2015，2018

lastupdated: "2018-11-12"

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:tip: .tip}
{:new_window: target="_blank"}

# Dedizierte ID mit öffentlicher IBMid verbinden
{: #connect_dedicated_id}

Bei der Anmeldung bei einer dedizierten Cloud, bei der der öffentliche IAM-Service verfügbar ist, werden Sie von der {{site.data.keyword.Bluemix_notm}}-Befehlszeilenschnittstelle dazu aufgefordert, sich mit Ihrer öffentlichen IBMid anstatt mit der dedizierten ID anzumelden.
{:shortdesc}

```
  $ ibmcloud login -a https://api.{dedicated_env}.cloud.ibm.com
  API-Endpunkt: https://api.{dedicated_env}.cloud.ibm.com

  Der öffentliche IAM-Token-Service ist in der dedizierten Umgebung verfügbar.
  Melden Sie sich mit Ihrer öffentlichen IBMid an oder verwenden Sie '--no-iam', wenn Sie sich nur als dedizierter Benutzer anmelden wollen.

  Email>
```

Wenn Ihre dedizierte ID bereits mit der öffentlichen IBMid verbunden ist, werden Authentifizierung und Anmeldung durchgeführt:

```
  Authentifizieren...
  OK

  Verbunden mit dediziertem Benutzer eigene_dedizierte_ID
```

Wenn Ihre dedizierte ID jedoch noch nicht mit der öffentlichen IBMid verbunden ist, werden Sie dazu aufgefordert, manuell eine Verbindung zu der öffentlichen IBMid herzustellen:

```
  Sie melden sich unter einer IBMid an, die keinem dedizierten Benutzer zugeordnet ist.
  Um die Verbindung herzustellen, müssen Sie die Berechtigungsnachweise des dedizierten Benutzers eingeben.

  Wählen Sie einen Berechtigungsnachweistyp aus:
  1. Benutzername und Kennwort
  2. Einmaliger Code (Abruf unter https://login.{dedicated_env}.cloud.ibm.com/passcode)
  Geben Sie eine Zahl ein. >
```

Wählen Sie eine Option aus, um die Berechtigungsnachweise für die dedizierte ID einzugeben. Nach der erfolgreichen Authentifizierung ist Ihre dedizierte ID nun mit Ihrer öffentlichen IBMid verbunden.

## Anmeldung bei einem lokalen UAA-Server erzwingen

Erzwingen Sie eine Anmeldung bei dem UAA-Server unter einer dedizierten ID, indem Sie die Option `--no-iam` beim Befehl `ibmcloud login` angeben:

```
  $ ibmcloud login --no-iam
```

## Verbindung zwischen dedizierter ID und öffentlicher IBMid aufheben 

Mit dem Befehl `ibmcloud iam dedicated-id-disconnect` können Sie die Verbindung zwischen der öffentlichen IBMid und der dedizierten ID aufheben.

```
  $ ibmcloud iam dedicated-id-disconnect
  Soll eigene_dedizierte_ID wirklich von der öffentlichen IBMid getrennt werden? (J/N)> j
  Dedizierter Benutzer 'eigene_dedizierte_ID' wird von öffentlicher IBMid getrennt...
  OK

  Abmelden...
  OK
```
