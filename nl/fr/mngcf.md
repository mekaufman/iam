---

copyright:

  years: 2017, 2019

lastupdated: "2019-01-28"

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}

# Gestion de l'accès Cloud Foundry
{: #mngcf}

Pour pouvoir gérer l'accès à des organisations et des espaces de compte, vous devez être le propriétaire du compte, le responsable de l'organisation ou le responsable de l'espace.
{:shortdesc}

## Mise à jour de l'accès Cloud Foundry
{: #update_cf_access}

1. Dans la barre de menus, cliquez sur **Gérer** &gt; **Accès (IAM)** puis sélectionnez **Utilisateurs**.
2. Sur la ligne de l'utilisateur auquel vous souhaitez affecter un accès, sélectionnez le menu **Actions** ![Icône Liste des actions](../icons/action-menu-icon.svg) puis cliquez sur **Affecter un accès**.
3. Sélectionnez **Affecter à l'aide de Cloud Foundry**.
4. Développez la ligne de l'organisation à laquelle l'utilisateur est affecté pour afficher l'accès de l'utilisateur aux espaces et à ses rôles dans ces espaces.
5. Dans le menu **Actions** ![Icône Liste des actions](../icons/action-menu-icon.svg) de la section Cloud Foundry, vous pouvez :

  * Retirer l'utilisateur de l'organisation
  * Editer le rôle d'organisation
  * Editer le rôle d'espace

## Ajout d'un utilisateur à une organisation
{: #add_to_org}

Si vous êtes le responsable d'une organisation dont l'utilisateur n'est pas encore membre, vous affectez l'utilisateur à cette organisation.

1. Dans la barre de menus, cliquez sur **Gérer** &gt; **Accès (IAM)** puis sélectionnez **Utilisateurs**.
2. Sur la ligne de l'utilisateur auquel vous souhaitez affecter un accès, sélectionnez le menu **Actions** ![Icône Liste des actions](../icons/action-menu-icon.svg) puis cliquez sur **Affecter un accès**.
3. Sélectionnez **Affecter à l'aide de Cloud Foundry**.
4. Sélectionnez **Affecter une organisation**.
5. Affectez l'accès utilisateur :
   * Sélectionnez une organisation à laquelle ajouter l'utilisateur
   * Affectez un rôle de l'organisation
   * Sélectionnez une région
   * Sélectionnez un espace
   * Affectez un rôle d'espace
7. Cliquez sur **Affecter**.

## Révision des accès affectés
{: #review_my_access}

Si vous devez vérifier l'accès qui vous a été affecté sur un compte auquel vous avez ajouté, procédez comme suit :

1. Dans la barre de menus, cliquez sur **Gérer** &gt; **Accès (IAM)** puis sélectionnez **Utilisateurs**.
2. Sélectionnez votre nom.
3. Cliquez sur **Accès Cloud Foundry**.
3. Développez la ligne de l'organisation puis consultez les rôles affectés.

Si vous avez besoin d'accès supplémentaires, vous devez contacter le responsable de votre organisation ou le propriétaire du compte afin de mettre à jour le rôle Cloud Foundry affecté.

