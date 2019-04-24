---

copyright:

  years: 2015, 2019
lastupdated: "2019-03-05"

keywords: application programming interface key, API key, API, classic infrastructure API key, IBM Cloud API key

subcollection: iam

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:tip: .tip}

# Description des clés d'API
{: #manapikey}

Une clé d'interface de programmation (clé d'API) est un code unique transmis à une interface de programmation (API) afin d'identifier l'application ou l'utilisateur appelant. Les clés d'API permettent de suivre et contrôler la façon dont l'API est utilisée, par exemple pour empêcher toute utilisation malveillante ou abusive de l'API. La clé d'API fait souvent office à la fois d'identificateur unique et de jeton confidentiel pour l'authentification. Elle dispose généralement de droits d'accès spécifiques à l'identité qui lui est associée.
{:shortdesc}

Pour voir vos clés d'API, accédez à **Gérer** > **Accès (IAM)** puis sélectionnez **Utilisateurs**.

## {{site.data.keyword.cloud_notm}}Clés d'API
{: #ibm-cloud-api-keys}

Les clés d'API {{site.data.keyword.cloud}} sont associées à l'identité de l'utilisateur. Seul l'utilisateur auquel la clé d'API est associée peut la créer et la supprimer. Vous pouvez utiliser les clés d'API {{site.data.keyword.cloud_notm}} dans l'interface de ligne de commande (CLI) ou dans le cadre de l'automatisation pour vous connecter sous votre identité d'utilisateur. Vous pouvez également utiliser les clés d'API {{site.data.keyword.cloud_notm}} pour accéder aux API d'infrastructure classique. Pour plus d'informations sur l'utilisation d'une clé d'API associée à votre identité utilisateur, voir[Gestion des clés d'API d'utilisateur](/docs/iam?topic=iam-userapikey#userapikey).

Vous pouvez également utiliser les clés d'API associées aux ID de service que vous créez. Les ID de service sont utilisés pour connecter une application à l'intérieur ou à l'extérieur de {{site.data.keyword.Bluemix_notm}} à un service {{site.data.keyword.Bluemix_notm}}. Pour plus d'informations sur la création de clés d'API associées à un ID de service, voir  [Gestion des clés d'API d'ID de service](/docs/iam?topic=iam-serviceidapikeys#serviceidapikeys).

## Autres types de clé d'API
{: #othertypes}

Outre vos clés d'API {{site.data.keyword.cloud_notm}}, il existe deux autres types de clé d'API que vous pouvez utiliser :

* clés d'API d'infrastructure classique
* clés d'API spécifiques au service

Les clés d'API d'infrastructure classique permettent d'appeler les API pour les services d'infrastructure classique. Vous ne pouvez créer qu'une seule clé d'API d'infrastructure classique à la fois. Vous pouvez créer une clé d'API de ce type pour un utilisateur sur la page Détails de l'utilisateur.

Les clés d'API {{site.data.keyword.cloud_notm}} permettent également d'accéder aux API d'infrastructure classique.
{: tip}

Certains services d'{{site.data.keyword.Bluemix_notm}} peuvent également fournir une clé d'API à utiliser avec le service. Par exemple, si vous affichez les détails d'une offre d'un service Watson à partir de votre liste de ressources, vous pouvez créer des données d'identification, qui incluent une clé d'API et une valeur confidentielle, spécifiques à ce service sur la page Données d'identification pour le service.
