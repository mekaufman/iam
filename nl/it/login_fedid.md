---

copyright:

  years: 2015，2019

lastupdated: "2019-03-27"

keywords: federated ID, enterprise SSO, single sign-on ID, API key login, one-time passcode login

subcollection: iam

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:tip: .tip}
{:new_window: target="_blank"}

# Accesso con un ID federato
{: #federated_id}

Come utente federato che utilizza un ID SSO (single sign-on) sociale o aziendale, puoi accedere a {{site.data.keyword.Bluemix}} dall'interfaccia riga di comando (o CLI, command-line interface) utilizzando un passcode monouso oppure una chiave API.
{: shortdesc}

## Utilizzo di un passcode monouso
{: #onetime_passcode}

Se utilizzi l'opzione di passcode monouso per accedere con un ID federato, devi specificare il parametro SSO (single-sign on) per ottenere un passcode monouso da immettere durante la fase di accesso.

Poiché un passcode monouso richiama il codice della console {{site.data.keyword.Bluemix_notm}}, l'utilizzo di un ID federato nello script di automazione provoca un errore. Evita il problema utilizzando l'opzione di chiave API con lo script automatizzato.
{: tip}

### Dalla CLI {{site.data.keyword.Bluemix_notm}}
{: #login_cli}
1. Specifica l'opzione `--sso` con il comando `ibmcloud login`.
2. Segui l'URL nel prompt per ottenere il passcode monouso.
3. Copia e incolla il valore del passcode nella CLI.

  ```
  ibmcloud login --sso
  Endpoint API: https://cloud.ibm.com

  Ottieni un codice monouso da https://identity-2.us-south.iam.cloud.ibm.com/identity/passcode per procedere.
  Aprire l'URL nel browser predefinito? [S/n]>
  Codice monouso >
  Autenticazione in corso...
  OK

  ```

### Dalla CLI Cloud Foundry
{: #login_cf_cli}

1. Specifica l'opzione `--sso` con il comando `cf login`.
2. Segui l'URL nel prompt per ottenere il passcode monouso.
3. Copia e incolla il valore del passcode nella CLI.

  ```
  cf login -a  https://api.us-south.cf.cloud.ibm.com --sso

  Endpoint API: https://api.us-south.cf.cloud.ibm.com

  Codice monouso (Ottienine uno a https://login.us-south.cf.cloud.ibm.com/UAALoginServerWAR/passcode)>
  Autenticazione in corso...
  OK

  ```

## Utilizzo di una chiave API
{: #api_key}

La chiave API richiesta è la chiave API {{site.data.keyword.Bluemix_notm}} utilizzata per l'autenticazione con la piattaforma {{site.data.keyword.Bluemix_notm}} e non la chiave API dell'infrastruttura classica o la chiave API del servizio {{site.data.keyword.Bluemix_notm}}.

1. Crea una chiave API con il [comando `ibmcloud iam api-key-create`](/docs/cli/reference/ibmcloud?topic=cloud-cli-ibmcloud_iam_api_key_create#ibmcloud_iam_api_key_create). Utilizza l'opzione `-f` per generare un file della chiave API invece di mostrare la chiave nella finestra di comando:

   ```
   ibmcloud iam api-key-create NOME [-d DESCRIZIONE] [-f, --file FILE]

   ```

2. Accedi con la chiave API.

  Puoi utilizzare la chiave API con la CLI {{site.data.keyword.Bluemix_notm}} in uno dei seguenti modi:

    * Chiama direttamente la chiave API.

      ```
      ibmcloud login --apikey <api_key_string>

      ```

    * Chiama la chiave API con il file della chiave:

      ```
      ibmcloud login --apikey @key_file_name

      ```

    * Imposta una variabile di ambiente. Puoi anche impostare una variabile di ambiente nel tuo sistema. Ad esempio, IBMCLOUD_API_KEY=api_key_string, dove `api_key_string` è il valore personalizzato della chiave API. Una volta impostata la variabile di ambiente, puoi semplicemente specificare `ibmcloud login` dalla CLI.

   Per Windows 10 PowerShell, vuoi utilizzare `'@key_file_name'` con il nome file della chiave racchiuso tra virgolette singole.
   {: tip}

  Per accedere utilizzando la CLI Cloud Foundry, specifica `apikey` come nome utente e la stringa della chiave API come password:

    ```
    cf login -a https://api.us-south.cf.cloud.ibm.com

    Endpoint API: https://api.us-south.cf.cloud.ibm.com

    Email> apikey

    Password>
Autenticazione in corso...
OK

    ```
