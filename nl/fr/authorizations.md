---

copyright:

  years: 2017, 2019

lastupdated: "2019-01-30"

keywords: authorizations, service to service access, access between services

subcollection: iam

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:tip: .tip}
{:note: .note}


# Octroi d'accès entre services
{: #serviceauth}

La plupart des fonctionnalités du système IAM (Identity and Access Management) {{site.data.keyword.Bluemix_notm}} se concentrent sur la gestion et l'application de l'accès aux ressources {{site.data.keyword.Bluemix_notm}} par les utilisateurs et leurs applications. Il existe toutefois d'autres scénarios dans lesquels vous pouvoir avoir besoin de fournir un service avec accès à une ressource d'un utilisateur dans un autre service. Tous les utilisateurs de votre compte peuvent créer une autorisation, mais seul un utilisateur disposant du rôle Administrateur peut supprimer une autorisation. Vous pouvez configurer et afficher des autorisations ayant été accordées dans votre compte sur la page **Autorisations**.
{:shortdesc}

## Création d'une autorisation
{: #create-auth}

Vous pouvez accorder uniquement le niveau d'accès dont vous disposez en tant qu'utilisateur du service cible. Ainsi, si vous n'avez qu'un accès Afficheur pour le service qui va être utilisé, vous ne pouvez accorder que le rôle Afficheur pour l'autorisation.

1. Dans la barre de menus, cliquez sur **Gérer** &gt; **Accès (IAM)** puis sélectionnez **Autorisations**.
2. Cliquez sur **Créer**.
3. Sélectionnez un service source et un service cible pour l'autorisation. Le service source se voit accorder l'accès au service cible sélectionné.
4. Sélectionnez un rôle pour affecter l'accès au service source lors de l'accès au service cible.
5. Cliquez sur **Autoriser**.

Seuls les services qui autorisent l'octroi de ce type d'accès sont disponibles en tant qu'options.
{: note}

## Retrait d'une autorisation
{: #remove-auth}

1. Dans la barre de menus, cliquez sur **Gérer** &gt; **Accès (IAM)** puis sélectionnez **Autorisations**.
2. Identifiez la ligne contenant l'autorisation que vous voulez retirer du compte.
3. Dans le menu **Actions** ![Icône Liste des actions](../icons/action-menu-icon.svg), sélectionnez **Retirer**.
5. Sélectionnez **Retirer**.
