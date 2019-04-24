---

copyright:

  years: 2018, 2019

lastupdated: "2019-01-30"

keywords: IBM Cloud service APIs, IAM token, API key, authenticate with service API

subcollection: iam

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:tip: .tip}

# Appel des API de service {{site.data.keyword.cloud_notm}}
{: #iamapikeysforservices}

Pour appeler un service {{site.data.keyword.Bluemix}} via une API, transmettez vos données d'identification à l'API du service afin d'authentifier votre identité utilisateur et votre accès pour effectuer des actions dans le contexte du service.
{:shortdesc}

Vous pouvez identifier l'appelant de l'une des façons suivantes :

* Clé d'API {{site.data.keyword.Bluemix_notm}} ou clé d'API d'ID de service
* Jeton {{site.data.keyword.Bluemix_notm}} IAM (Identity and Access Management)

[Les clés d'API {{site.data.keyword.Bluemix_notm}}](/docs/iam?topic=iam-userapikey#userapikey), les [clés d'API d'ID de service](/docs/iam?topic=iam-serviceidapikeys#serviceidapikeys) et les jetons IAM identifient de manière unique l'identité de l'appelant.  Il s'agit d'un utilisateur {{site.data.keyword.Bluemix_notm}} ou d'un ID de service créé dans un compte {{site.data.keyword.Bluemix_notm}}.

Les clés d'API sont des données d'identification composées d'une longue série de caractères aléatoires. Une identité {{site.data.keyword.Bluemix_notm}} peut avoir plusieurs clés d'API. Chacune de ces clés d'API peut être gérée indépendamment, ce qui signifie que si cette clé d'API est utilisée par votre service uniquement, vous pouvez supprimer la clé d'API sans interrompre d'autre composant.

Vous pouvez utiliser des clés d'API pour [vous connecter à l'interface de ligne de commande (CLI) {{site.data.keyword.Bluemix_notm}}](/docs/cli/reference/ibmcloud?topic=cloud-cli-ibmcloud_login#ibmcloud_login) ou pour [générer des jetons IAM](/docs/iam?topic=iam-iamtoken_from_apikey#iamtoken_from_apikey). Alors que cela n'est pas recommandé pour la production, vous pouvez également envoyer des clés d'API à des services {{site.data.keyword.Bluemix_notm}}.

## Transmission d'une clé d'API {{site.data.keyword.Bluemix_notm}} pour l'authentification avec une API de service
{: #apikey_auth}

Les clients d'API peuvent transmettre directement une clé d'API {{site.data.keyword.Bluemix_notm}} à l'API du service cible. Pour ce faire, envoyez au service cible le mot clé `apikey` en tant que nom d'utilisateur et la clé d'API {{site.data.keyword.Bluemix_notm}} en tant que mot de passe en utilisant l'en-tête HTTP d'autorisation.

L'API du service cible doit introspecter la clé d'API {{site.data.keyword.Bluemix_notm}} en utilisant le service IAM {{site.data.keyword.Bluemix_notm}}. Le graphique suivant présente trois interactions d'API. La clé d'API {{site.data.keyword.Bluemix_notm}} est transmise à l'API de chaque service cible, ainsi chaque service cible doit rechercher les détails de clé d'API {{site.data.keyword.Bluemix_notm}} en appelant {{site.data.keyword.Bluemix_notm}} IAM.

![Authentification avec une API de service en utilisant une clé d'API ](images/APIkeyauth.svg "Transmission de clés d'API à des services cible qui transmettent ensuite la clé d'API à IAM pour valider les données d'identification")

L'utilisation d'une clé d'API {{site.data.keyword.Bluemix_notm}} est recommandée. Vous pouvez ainsi détecter rapidement de nouvelles API et essayer rapidement des prototypes. Cette méthode exige que vous envoyiez la clé d'API {{site.data.keyword.Bluemix_notm}} à l'API du service cible à un format lisible, ce qui compromet de manière inutile la clé d'API. De plus, comme l'API du service cible doit toujours introspecter la clé d'API, cette méthode est moins performante et n'est donc pas recommandée pour les charges de travail de production.

Pour l'authentification via l'API d'un service en utilisant une clé d'API, procédez comme suit :

  1. Tout d'abord, [créez une clé d'API {{site.data.keyword.Bluemix_notm}}](/docs/iam?topic=iam-userapikey#creating-an-api-key) si vous n'en avez pas encore.
  2. Envoyez la clé d'API {{site.data.keyword.Bluemix_notm}}, comme cela est défini sur la page [RFC 7617](https://tools.ietf.org/html/rfc7617){: new_window} ![Icône de lien externe](../icons/launch-glyph.svg "Icône de lien externe"), sous la forme d'en-tête HTTP “Authorization”. Utilisez `apikey` en tant que nom d'utilisateur et la valeur de clé d'API en tant que mot de passe.

Dans la procédure suivante, il est supposé que la clé d'API est 0a1A2b3B4c5C6d7D8e9E :

  1.	Concaténez le nom d'utilisateur `apikey` et la clé d'API en les séparant par le signe deux points : `apikey:0a1A2b3B4c5C6d7D8e9E`
  2.	Codez en Base64 la chaîne suivante : `base64("apikey:0a1A2b3B4c5C6d7D8e9E") => YXBpa2V5OjBhMUEyYjNCNGM1QzZkN0Q4ZTlF`
  3.	Définissez l'autorisation d'en-tête HTTP avec le schéma basique, par exemple `Authorization: Basic YXBpa2V5OjBhMUEyYjNCNGM1QzZkN0Q4ZTlF`. Lorsque vous utilisez la commande curl, vous pouvez transmettre cet élément avec le paramètre -u :

    ```
    curl -u "apikey:<IBM Cloud API key value>"
    ```

  Si vous utilisez d'autres outils, il peut être nécessaire de spécifier différemment ces données d'identification.
  {: tip}

## Transmission d'un jeton {{site.data.keyword.Bluemix_notm}} IAM pour l'authentification avec une API de service
{: #token_auth}

Pour extraire un jeton d'accès IAM, le client API doit tout d'abord appeler une API {{site.data.keyword.Bluemix_notm}} IAM pour authentifier et extraire ce jeton. La méthode recommandée pour les clients d'API de service {{site.data.keyword.Bluemix_notm}} consiste à utiliser une clé d'API IAM pour obtenir un jeton d'accès IAM. Ce dernier peut être utilisé pour plusieurs appels de services {{site.data.keyword.Bluemix_notm}} qui acceptent les jetons d'accès IAM comme méthode d'authentification. Comme les jetons d'accès IAM sont signés numériquement avec des clés asymétriques, les services {{site.data.keyword.Bluemix_notm}} peuvent valider un jeton d'accès IAM sans appeler de service externe. Cela permet d'améliorer considérablement les performances de l'appel d'une API.

![Authentification avec une API de service en utilisant un jeton d'accès ](images/tokenauth.svg "Extraction d'un jeton à partir d'IAM en utilisant une clé d'API et en transmettant le jeton d'accès à des services cible pour valider les données d'identification")

Pour l'authentification via l'API d'un service en utilisant un jeton d'accès, procédez comme suit :

  1. Tout d'abord, [créez une clé d'API {{site.data.keyword.Bluemix_notm}}](/docs/iam?topic=iam-userapikey#creating-an-api-key) si vous n'en avez pas encore.
  2. L'étape suivante pour le client API est l'extraction d'un jeton d'accès IAM, comme cela est décrit dans la rubrique [Obtention d'un jeton IBM Cloud IAM  à l'aide d’une clé d'API](/docs/iam?topic=iam-iamtoken_from_apikey#iamtoken_from_apikey).
  3. A partir de la réponse, extrayez la propriété `access_token` pour obtenir le jeton d'accès IAM. `expires_in` indique le nombre de secondes avant l'expiration du jeton d'accès IAM `access_token`. Utilisez cette valeur relative ou l'`expiration` de l'horodatage absolu en [temps UNIX](https://en.wikipedia.org/wiki/Unix_time){: new_window} ![Icône de lien externe](../icons/launch-glyph.svg "Icône de lien externe").
  4. Envoyez le jeton d'accès IAM, comme cela est décrit sur la page [RFC 6750, section 2.1. Authorization Request Header Field](https://tools.ietf.org/html/rfc6750#page-5){: new_window} ![Icône de lien externe](../icons/launch-glyph.svg "Icône de lien externe"):

Consultez l'exemple suivant :

  1.	Utilisez l'autorisation d'en-tête HTTP
  2.	Préfixez le jeton d'accès IAM avec le littéral `Bearer: Bearer eyJhbGciOiJSUzI1Ng...`
  3.	Ajoutez le jeton d'accès IAM préfixé à l'en-tête HTTP : `Authorization: Bearer eyJhbGciOiJSUzI1Ng...`. Lorsque vous utilisez la commande curl, vous pouvez transmettre cet élément avec le paramètre -H :

    ```
    curl -H "Authorization: Bearer eyJhbGciOiJSUzI1Ng..."
    ```

  Utilisez le jeton d'accès IAM pour les appels de service IBM Cloud suivants afin de garantir l'évolutivité et pour de meilleures performances.
  {: tip}
