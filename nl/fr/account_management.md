---

copyright:

  years: 2019

lastupdated: "2019-06-03"

keywords: account management, access, access policy, account administrator

subcollection: iam

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:tip: .tip}
{:note: .note}

# Affectation de l'accès aux services de gestion de compte
{: #account-services}

En tant que propriétaire de compte ou administrateur d'un service de gestion des comptes, vous pouvez utiliser ces services pour permettre aux utilisateurs du compte d'inviter des utilisateurs à rejoindre ce dernier, d'effectuer le suivi de la facturation et de l'utilisation ainsi que d'utiliser des cas de support. Les utilisateurs disposant de l'accès peuvent également gérer des ID de service, des règles d'accès, des entrées de catalogue et des groupes d'accès.

## Création de règles pour l'accès au service de gestion des comptes
{: #account-management-access}

Pour attribuer l'accès à l'un ou à tous les services de gestion de compte, procédez comme suit :

1. Dans la barre de menus, cliquez sur **Gérer** &gt; **Accès (IAM)** puis sélectionnez **Utilisateurs**.
2. Sur la ligne de l'utilisateur auquel vous souhaitez affecter un accès, sélectionnez le menu **Actions** ![Icône Liste des actions](../icons/action-menu-icon.svg) puis cliquez sur **Affecter un accès**.
3. Choisissez d'affecter l'accès aux **Services de gestion des comptes**.
4. Sélectionnez **Tous les services de gestion des comptes** ou bien un service de gestion de compte spécifique.
5. Sélectionnez toute combinaison de rôles pour affecter l'accès voulu.

Pour accorder à un autre utilisateur l'accès complet au compte à des fins de gestion des accès utilisateur et de gestion de toutes les ressources de compte, vous devez affecter deux règles. La première octroie à l'utilisateur l'accès à toutes les ressources en sélectionnant **Tous les services avec l'offre Identity and Access activée** avec les rôles **Administrateur** et **Responsable** affectés. L'autre règle octroie à l'utilisateur l'accès à tous les services de gestion des comptes en sélectionnant **Tous les services de gestion des comptes** avec le rôle **Administrateur** affecté.
{: tip}

## Mappages action/rôle pour les services de gestion des comptes
{: #account-management-actions-roles}

Le tableau suivant met en avant les actions pouvant être effectuées par les utilisateurs lorsqu'un rôle spécifique est affecté pour chaque service de gestion des comptes. Consultez les informations afin de vous assurer que vous affectez le niveau d'accès correct à vos utilisateurs.

| Rôles | Actions |
|:-------|----------|
| Afficheur |   Afficher des groupes d'accès et des membres     |
| Opérateur | Non applicable    |
| Editeur |  Afficher, créer, éditer et supprimer des groupes <br><br> Ajouter ou supprimer des utilisateurs dans des groupes     |
| Administrateur |  Afficher, créer, éditer et supprimer des groupes <br><br> Ajouter ou supprimer des utilisateurs <br><br> Affecter l'accès à un groupe <br><br> Gérer l'accès pour utiliser des groupes d'accès   |
{: caption="Tableau 1. Rôles et actions pour le service Groupes d'accès" caption-side="top"}

| Rôles | Actions |
|:-------|----------|
| Afficheur |  Afficher les utilisateurs du compte <br><br> Afficher les paramètres du profil utilisateur     |
| Opérateur | Afficher les utilisateurs du compte <br><br> Afficher les paramètres du profil utilisateur  |
| Editeur |  Afficher, inviter, retirer et mettre à jour des utilisateurs dans le compte <br><br> Afficher et mettre à jour les paramètres de profil utilisateur    |
| Administrateur | Afficher, inviter, retirer et mettre à jour des utilisateurs dans le compte <br><br> Afficher et mettre à jour les paramètres de profil utilisateur    |
{: caption="Tableau 2. Rôles et actions pour le service Gestion des utilisateurs" caption-side="top"}

| Rôles | Actions |
|:-------|----------|
| Afficheur |  Afficher les cas de support <br><br> Rechercher des cas de support      |
| Opérateur |  Non applicable    |
| Editeur |  Afficher les cas de support <br><br> Rechercher des cas de support <br><br> Mettre à jour les cas <br><br> Créer des cas     |
| Administrateur |  Afficher les cas de support <br><br> Rechercher des cas de support <br><br> Mettre à jour les cas <br><br> Créer des cas    |
{: caption="Tableau 3. Rôles et actions pour le service Centre de support" caption-side="top"}

{: #billing-acct-mgmt}
| Rôles | Actions |
|:-------|----------|
| Afficheur | Afficher les paramètres des fonctions du compte <br><br> Afficher les abonnements dans le compte <br><br> Afficher le nom du compte <br><br> Afficher les groupes de ressources   |
| Opérateur | Afficher les paramètres des fonctions du compte <br><br> Afficher les abonnements dans le compte <br><br> Afficher et modifier le nom du compte <br><br> Afficher et mettre à jour les groupes de ressources    |
| Editeur |  Afficher et mettre à jour les paramètres de fonctions du compte <br><br> Afficher les abonnements dans le compte <br><br> Afficher les offres dans le compte <br><br> Afficher et appliquer les codes de fonction <br><br> Afficher et modifier le nom du compte <br><br> Afficher et mettre à jour le plafond des dépenses <br><br> Afficher, créer et mettre à jour les groupes de ressources    |
| Administrateur |  Afficher et mettre à jour les paramètres de fonctions du compte <br><br> Afficher les abonnements dans le compte <br><br> Afficher les offres dans le compte <br><br> Afficher et appliquer les codes de fonction <br><br> Afficher et modifier le nom du compte <br><br> Afficher et mettre à jour le plafond des dépenses <br><br> Afficher le solde des abonnements et effectuer le suivi de l'utilisation <br><br> Afficher, créer, mettre à jour et affecter un accès pour la gestion des groupes de ressources  |
{: caption="Tableau 4. Rôles et action pour le service Facturation" caption-side="top"}

| Rôles | Actions |
|:-------|----------|
| Afficheur |   Afficher les ID     |
| Opérateur | Créer et supprimer des ID et des clés d'API   |
| Editeur |  Créer, mettre à jour et supprimer des ID et clés d'API  |
| Administrateur |  Créer, mettre à jour et supprimer des ID et clés d'API <br><br> Affecter des règles d'accès aux ID  |
{: caption="Tableau 5. Rôles et actions pour le service d'identité IAM" caption-side="top"}
{: #identity-service-acct-mgmt}

Pour le service d'identité IAM, ces actions s'appliquent aux ID de service dans le compte que l'utilisateur n'a pas créés. Tous les utilisateurs peuvent créer des ID de service. Ils sont administrateurs de ces ID et ils peuvent créer la clé d'API et les règles d'accès associées. Toutefois, ce service de gestion des comptes s'applique à la possibilité d'afficher, de supprimer et d'affecter l'accès aux ID de service dans le compte créé par d'autres utilisateurs.
{: note}

| Rôles | Actions |
|:-------|----------|
| Afficheur |   Afficher les services privés    |
| Opérateur | Non applicable    |
| Editeur |   Peut changer les métadonnées d'objet mais ne peut pas changer la visibilité des services privés     |
| Administrateur |  Peut changer les métadonnées d'objet ou la visibilité des services privés et peut restreindre la visibilité d'un service public   |
{: caption="Tableau 6. Rôles et actions pour le service de catalogue global" caption-side="top"}

| Rôles | Actions |
|:-------|----------|
| Afficheur |  Toutes les actions du rôle Afficheur pour les services de gestion de compte     |
| Opérateur |  Toutes les actions du rôle Opérateur pour les services de gestion de compte     |
| Editeur |  Toutes les actions du rôle Editeur pour les services de gestion de compte et possibilité de créer des groupes de ressources    |
| Administrateur |  Toutes les actions du rôle Administrateur pour les services de gestion de compte et possibilité de créer des groupes de ressources    |
{: caption="Tableau 7. Rôles et action pour une règle s'appliquant à tous les services d'identité et d'accès" caption-side="top"}
