---

copyright:

  years: 2018, 2019

lastupdated: "2019-05-16"

keywords: event tracking, IAM events, monitoring

subcollection: iam

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:tip: .tip}
{:note: .note}
{:deprecated: .deprecated}

# Suivi des événements IAM
{: #tracking}

En tant que responsable de la sécurité, auditeur ou responsable, vous pouvez utiliser le service {{site.data.keyword.at_full}} pour suivre comment les utilisateurs et les applications interagissent avec {{site.data.keyword.Bluemix_notm}} Identity and Access Management (IAM).
{:shortdesc}

Depuis le 9 mai 2019 le service {{site.data.keyword.cloudaccesstraillong}} est obsolète. Vous devez créer une instance {{site.data.keyword.at_short}} dans votre compte pour continuer à suivre les événements IAM. Pour plus d'informations, voir [Obsolescence du service IBM Cloud Activity Tracker](https://www.ibm.com/blogs/cloud-archive/2019/04/deprecating-ibm-cloud-activity-tracker/){: new_window} ![Icône de lien externe](../icons/launch-glyph.svg "Icône de lien externe").
{: deprecated}

Vous pouvez effectuer le suivi des événements suivants :

* Gestion de groupes d'accès en créant et supprimant des groupes ou en ajoutant et retirant des utilisateurs
* Création, mise à jour ou suppression d'ID de service
* Création, mise à jour ou suppression de clés d'API
* Création, mise à jour ou suppression de règles d'accès
* Connexion à {{site.data.keyword.Bluemix_notm}} en utilisant une clé d'API, un code d'autorisation, un code d'accès, une clé d'API ou un mot de passe associé à un ID de service.

Pour commencer à surveiller les actions utilisateur, voir [{{site.data.keyword.at_short}}](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-getting-started#getting-started). Pour plus d'informations sur les différentes zones d'événement dont vous pouvez effectuer le suivi, voir [Evénements IAM](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-at_events_iam).
