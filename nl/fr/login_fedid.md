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

# Connexion à l'aide d'un ID fédéré
{: #federated_id}

En tant qu'utilisateur fédéré utilisant un ID de connexion d'entreprise, vous pouvez vous connecter à {{site.data.keyword.Bluemix}} à partir de l'interface de ligne de commande en utilisant un code d'accès à utilisation unique ou une clé d'API.
{: shortdesc}

## Utilisation d'un code d'accès à utilisation unique
{: #onetime_passcode}

Lorsque vous choisissez d'utiliser un code d'accès à utilisation unique pour vous connecter à l'aide d'un ID fédéré, vous spécifiez le paramètre de connexion unique (SSO) afin d'obtenir le code d'accès à utilisation unique, puis vous tapez celui-ci pour vous connecter.

Etant donné qu'un code d'accès à utilisation unique extrait du code de la console {{site.data.keyword.Bluemix_notm}}, l'utilisation d'un ID fédéré dans votre script d'automatisation échoue. Pour éviter tout incident, choisissez d'utiliser une clé d'API avec un script d'automatisation.
{: tip}

### Depuis l'interface de ligne de commande de {{site.data.keyword.Bluemix_notm}}
{: #login_cli}
1. Spécifiez l'option `--sso` avec la commande `ibmcloud login`.
2. Suivez l'URL dans l'invite afin d'obtenir le code d'accès à utilisation unique.
3. Copiez et collez la valeur de code d'accès dans l'interface de ligne de commande comme valeur d'entrée.

  ```
  ibmcloud login --sso
  API endpoint: https://cloud.ibm.com

  Get One Time Code from https://identity-2.us-south.iam.cloud.ibm.com/identity/passcode to proceed.
  Open the URL in the default browser? [Y/n]>
  One Time Code >
  Authenticating...
  OK

  ```

### Depuis l'interface de ligne de commande de Cloud Foundry
{: #login_cf_cli}

1. Spécifiez l'option `--sso` à l'aide de la commande `cf login`.
2. Suivez l'URL dans l'invite afin d'obtenir le code d'accès à utilisation unique.
3. Copiez et collez la valeur de code d'accès dans l'interface de ligne de commande comme valeur d'entrée.

  ```
  cf login -a  https://api.us-south.cf.cloud.ibm.com --sso

  API endpoint: https://api.us-south.cf.cloud.ibm.com

  One Time Code (Get one at https://login.us-south.cf.cloud.ibm.com/UAALoginServerWAR/passcode)>
  Authenticating...
  OK

  ```

## Utilisation d'une clé d'API
{: #api_key}

La clé d'API requise est la clé d'API {{site.data.keyword.Bluemix_notm}} utilisée pour l'authentification auprès de la plateforme {{site.data.keyword.Bluemix_notm}} et non la clé d'API de l'infrastructure classique ou la clé d'API de service {{site.data.keyword.Bluemix_notm}}.

1. Créez une clé d'API à l'aide de la commande [`ibmcloud iam api-key-create`](/docs/cli/reference/ibmcloud?topic=cloud-cli-ibmcloud_commands_iam#ibmcloud_iam_api_key_create). Utilisez l'option `-f` pour générer un fichier de clés d'API au lieu d'afficher la clé dans la fenêtre de commande :

   ```
   ibmcloud iam api-key-create NAME [-d DESCRIPTION] [-f, --file FILE]

   ```

2. Connectez-vous à l'aide de la clé d'API.

  Vous pouvez utiliser la clé d'API à l'aide de l'interface de ligne de commande de {{site.data.keyword.Bluemix_notm}} en procédant de l'une des façons suivantes :

    * Appelez la clé d'API directement :

      ```
      ibmcloud login --apikey <api_key_string>

      ```

    * Appelez la clé d'API à l'aide du fichier de clés :

      ```
      ibmcloud login --apikey @key_file_name

      ```

    * Configurez une variable d'environnement. Vous pouvez également définir une variable d'environnement sur votre système. Par exemple, IBMCLOUD_API_KEY=api_key_string, où `api_key_string` est la valeur personnalisée de la clé d'API. Une fois la variable d'environnement définie, il vous suffit de spécifier `ibmcloud login` depuis l'interface de ligne de commande.

   Pour Windows 10 PowerShell, vous devez utiliser `'@key_file_name'` avec des apostrophes autour du nom du fichier de clés.
   {: tip}

  Pour vous connecter à l'aide de l'interface de ligne de commande de Cloud Foundry, spécifiez `apikey` comme nom d'utilisateur et la chaîne de clé d'API comme mot de passe :

    ```
    cf login -a https://api.us-south.cf.cloud.ibm.com

    API endpoint: https://api.us-south.cf.cloud.ibm.com

    Email> apikey

    Password>
    Authenticating...
    OK

    ```
