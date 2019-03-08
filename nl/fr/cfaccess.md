---

copyright:

  years: 2017, 2019

lastupdated: "2019-01-28"

keywords: Cloud Foundry roles, Cloud Foundry access, auditor, manager, developer, billing manager

subcollection: iam

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:tip: .tip}
{:note: .note}

# Accès Cloud Foundry
{: #cfaccess}

Actuellement, les services ne peuvent pas tous être gérés à l'aide de Cloud IAM. Vous pouvez continuer à utiliser des rôles Cloud Foundry permettant d'accéder à ces instances de service. Les utilisateurs sont ajoutés à l'organisation et à l'espace auxquels l'instance appartient avec un rôle Cloud Foundry affecté.
{:shortdesc}


![Accès à l'aide d'organisations et d'espaces Cloud Foundry dans un compte](images/cf-diagram.svg "Fonctionnement des accès dans un compte à l'aide d'organisations, d'espaces et de rôles Cloud Foundry")


## Rôles Cloud Foundry
{: #cfroles}

Les rôles Cloud Foundry accordent l'accès à des organisations et des espaces d'un compte. Les rôles Cloud Foundry n'activent pas de droits utilisateur permettant de réaliser des actions dans le contexte d'un service du compte.

Les rôles suivants peuvent être affectés au niveau de l'organisation :

| Rôle d'organisation | Droits |
|-------------------|-------------|
|Responsable | Les responsables de l'organisation peuvent créer, visualiser, éditer ou supprimer des espaces dans celle-ci, examiner l'utilisation et le quota de l'organisation, inviter des utilisateurs dans l'organisation, désigner les utilisateurs y ayant accès et leurs rôles, ainsi que les domaines personnalisés de l'organisation. |
|Responsable de la facturation | Un responsable de la facturation peut afficher des informations sur l'utilisation des contextes d'exécution et des services pour l'organisation dans la page Tableau de bord de l'utilisation.  |
|Auditeur | Un auditeur de l'organisation peut afficher le contenu des applications et des services dans l'organisation. Il peut également afficher les utilisateurs dans l'organisation et les rôles qui leur sont affectés, ainsi que le quota pour l'organisation. |
{:caption="Tableau 1. Rôles d'organisation et droits" caption-side="top"}

Les rôles suivants peuvent être affectés au niveau de l'espace :

| Rôle d'espace | Droits |
|------------|-------------|
|Responsable | Un responsable de l'espace peut ajouter des utilisateurs existants et gérer les rôles dans l'espace. Il peut également afficher le nombre d'instances, les liaisons de service et l'utilisation des ressources pour chaque application dans l'espace. |
|Développeur | Un développeur de l'espace peut créer, supprimer et gérer des applications et des services dans l'espace. Certaines tâches de gestion impliquent le déploiement d'applications, le démarrage ou l'arrêt d'applications, le changement de nom d'une application, la suppression d'une application, le changement de nom d'un espace, la liaison d'un service ou l'annulation de la liaison d'un service à une application ainsi que l'affichage du nombre d'instances, des liaisons de service et de l'utilisation des ressources pour chaque application dans l'espace. De plus, le développeur de l'espace peut associer une adresse URL interne ou externe à une application dans l'espace.   |
|Auditeur | Un auditeur de l'espace dispose de l'accès en lecture à toutes les informations sur l'espace, telles que le nombre d'instances, les liaisons de service et l'utilisation des ressources pour chaque application dans l'espace. |
{:caption="Tableau 2. Rôles d'espace et droits" caption-side="top"}

Les utilisateurs auxquels le rôle de responsable ou de développeur est affecté peuvent accéder à la variable d'environnement VCAP_SERVICES. Toutefois, un utilisateur possédant le rôle d'auditeur ne peut pas y accéder.
{: note}
