---



copyright:

  years: 2015，2019

lastupdated: "2019-02-13"

keywords: dedicated ID, public IBMid, IBMid, public IAM service

subcollection: iam

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:tip: .tip}
{:new_window: target="_blank"}

# Dedizierte ID mit öffentlicher IBMid verbinden
{: #connect_dedicated_id}

Für die Anmeldung bei einer dedizierten Cloud, in der der öffentliche IAM-Service verfügbar ist, müssen Sie sich bei der {{site.data.keyword.Bluemix_notm}}-Befehlszeilenschnittstelle mit Ihrer öffentlichen IBMid anmelden, nicht mit der dedizierten ID.
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
  1. Benutzername und Kennwort.
  2. Einmaliger Code. Dieser kann über https://login.{dedicated_env}.cloud.ibm.com/passcode) abgerufen werden.
  Geben Sie eine Zahl ein. >
```

Wählen Sie eine Option aus, um die Berechtigungsnachweise für die dedizierte ID einzugeben. Nach der erfolgreichen Authentifizierung ist Ihre dedizierte ID nun mit Ihrer öffentlichen IBMid verbunden.

## Anmeldung bei einem lokalen UAA-Server erzwingen
{: #force_login}

Erzwingen Sie eine Anmeldung bei dem UAA-Server unter einer dedizierten ID, indem Sie die Option `--no-iam` beim Befehl `ibmcloud login` angeben:

```
  $ ibmcloud login --no-iam
```

## Verbindung zwischen dedizierter ID und öffentlicher IBMid aufheben
{: #disconnect_id}

Mit dem Befehl `ibmcloud iam dedicated-id-disconnect` können Sie die Verbindung zwischen der öffentlichen IBMid und der dedizierten ID aufheben.

```
  $ ibmcloud iam dedicated-id-disconnect
  Soll eigene_dedizierte_ID wirklich von der öffentlichen IBMid getrennt werden? (J/N)> j
  Dedizierter Benutzer 'eigene_dedizierte_ID' wird von öffentlicher IBMid getrennt...
  OK

  Abmelden...
  OK
```
