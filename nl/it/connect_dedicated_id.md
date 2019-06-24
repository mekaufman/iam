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

# Connessione di un ID dedicato al tuo ID IBM pubblico
{: #connect_dedicated_id}

Per accedere a un cloud dedicato in cui è disponibile il servizio IAM pubblico, devi accedere alla CLI {{site.data.keyword.Bluemix_notm}} utilizzando il tuo ID IBM pubblico anziché l'ID dedicato.
{:shortdesc}

```
  $ ibmcloud login -a https://api.{dedicated_env}.cloud.ibm.com
  API endpoint: https://api.{dedicated_env}.cloud.ibm.com

  Il servizio del token IAM pubblico è disponibile nell'ambiente dedicato.
  Accedi con il tuo ID IBM pubblico o utilizza '--no-iam' per effettuare l'accesso solo come utente dedicato.

  Email>
```

Se il tuo ID dedicato è già connesso all'ID IBM pubblico, esegue l'autenticazione e l'accesso:

```
  Autenticazione in corso...
  OK

  Connesso all'utente dedicato my_dedicated_id
```

Tuttavia, se il tuo ID dedicato non è connesso all'ID IBM pubblico, ti viene richiesto di connetterti manualmente all'ID IBM pubblico:

```
  Stai eseguendo l'accesso con un ID IBM che non è associato ad alcun utente dedicato.
  Per configurare la connessione, immetti le credenziali dell'utente dedicato.

  Scegli un tipo di credenziale:
  1. Nome utente e password
  2. Codice monouso. Puoi ottenerne uno in https://login.{dedicated_env}.cloud.ibm.com/passcode)
  Immetti un numero>
```

Seleziona un'opzione per immettere le credenziali per l'ID dedicato. Dopo aver eseguito correttamente l'autenticazione, il tuo ID dedicato viene connesso al tuo ID IBM pubblico.

## Forza l'accesso al server UAA locale
{: #force_login}

Per forzare l'accesso al server UAA con un ID dedicato, specifica l'opzione `--no-iam` nel comando `ibmcloud login`:

```
  $ ibmcloud login --no-iam
```

## Disconnetti il tuo ID dedicato dall'ID IBM pubblico
{: #disconnect_id}

Puoi utilizzare `ibmcloud iam dedicated-id-disconnect` per disconnettere l'ID IBM pubblico dall'ID dedicato.

```
  $ ibmcloud iam dedicated-id-disconnect
  Desideri veramente disconnettere my_dedicated_id dall'ID IBM pubblico? (S/N)> s
  Disconnessione utente dedicato my_dedicated_id dall'ID IBM pubblico...
  OK

  Disconnessione in corso...
  OK
```
