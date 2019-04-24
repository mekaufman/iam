---



copyright:

  years: 2015，2019

lastupdated: "2019-02-13"

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:tip: .tip}
{:new_window: target="_blank"}

# Connexion d'un ID dédié à votre IBMid public
{: #connect_dedicated_id}

Pour vous connecter à un cloud dédié où le service IAM public est disponible, l'interface de ligne de commande {{site.data.keyword.Bluemix_notm}} vous demande de vous connecter en utilisant votre IBMid public et non l'ID dédié.
{:shortdesc}

```
  $ ibmcloud login -a https://api.{dedicated_env}.cloud.ibm.com
  API endpoint: https://api.{dedicated_env}.cloud.ibm.com

  Public IAM token service is available in the dedicated environment.
  Login with your public IBMid, or use '--no-iam' to login as a dedicated user only.

  E-mail>
```

Si votre ID dédié est déjà connecté à l'IBMid public, il s'authentifie et se connecte :

```
  Authenticating...
  OK

  Connected to dedicated user my_dedicated_id
```

Toutefois, si votre ID dédié n'a pas été connecté à l'IBMid public, vous êtes invité à vous connecter manuellement à l'IBMid public :

```
  You are logging with an IBMid that does not associated with any dedicated user.
  To set up the connection, input the credentials of the dedicated user.

  Choose a credential type:
  1. Username and password
  2. One Time Code (Get one at https://login.{dedicated_env}.cloud.ibm.com/passcode)
  Enter a number>
```

Sélectionnez une option pour l'entrée des données d'identification pour l'ID dédié. Après une authentification réussie, votre ID dédié est connecté à votre ID public.

## Comment forcer une connexion au serveur UAA local ?
{: #force_login}

Pour forcer une connexion au serveur UAA avec un ID dédié, spécifiez l'option `--no-iam` dans la commande `ibmcloud login` :

```
  $ ibmcloud login --no-iam
```

## Déconnexion de votre ID dédié depuis l'IBMid public 
{: #disconnect_id}

Vous pouvez utiliser la commande `ibmcloud iam dedicated-id-disconnect` pour déconnecter l'IBMid public avec l'ID dédié connecté.

```
  $ ibmcloud iam dedicated-id-disconnect
  Do you really want to disconnect my_dedicated_id from public IBMid? (Y/N)> y
  Disconnecting dedicated user my_dedicated_id from public IBMid...
  OK

  Logging out...
  OK
```
