---

copyright:

  years: 2015, 2019
lastupdated: "2019-05-01"

keywords: service ID, service ID access, managing access for service IDs

subcollection: iam

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:tip: .tip}
{:note: .note}

# Gestion des règles d'accès associées aux ID de service
{: #serviceidpolicy}

Lorsque vous créez un ID de service, vous pouvez affecter des règles de service à cet ID de service afin de contrôler le niveau d'accès autorisé lorsqu'il est utilisé pour l'authentification avec vos services. Vous pouvez mettre à jour les règles d'accès affectées à tout moment en changeant une règle existante, en supprimant une règle ou en en affectant une nouvelle.
{:shortdesc}

Le fait de supprimer ou d'éditer une règle existante pour un ID de service en cours d'utilisation peut entraîner une interruption de service.
{: note}

## Affectation d'un nouvel accès
{: #access_new}

Pour affecter des droits d'accès à toutes les ressources d'un groupe de ressources ou uniquement à un service d'un groupe de ressources, procédez comme suit :

1. Dans la barre de menus, cliquez sur **Gérer** &gt; **Accès (IAM)** puis sélectionnez **ID de service**.
2. Sélectionnez l'ID de service pour laquelle vous souhaitez affecter une règle de service.
3. Cliquez sur **Règles d'accès**.
4. Cliquez sur **Affecter un accès**.
5. Sélectionnez l'option d'affectation par groupe de ressources****.
6. Sélectionnez un groupe de ressources.
7. Sélectionnez un rôle dans la zone **Affecter l'accès à un groupe de ressources**. Cette option permet à l'utilisateur d'afficher le groupe de ressources sur sa liste de ressources, d'éditer le nom du groupe de ressources ou de gérer l'accès des utilisateurs au groupe. Vous pouvez sélectionner **Aucun accès** si vous souhaitez que l'utilisateur ait accès uniquement à la ressources que vous indiquez et non au groupe auquel elle est affectée.
8. Sélectionnez un service dans le groupe de ressources ou sélectionnez d'accorder l'accès à tous les services du groupe sélectionné.
9. Sélectionnez toute combinaison de rôles pour affecter l'accès voulu à l'utilisateur. Cet accès s'applique uniquement aux ressources sélectionnées pour la règle. Il n'accorde pas l'accès au conteneur réel constitué par le groupe de ressources.
10. Sélectionnez **Affecter**.

Pour affecter des droits d'accès à une ressource individuelle du compte, procédez comme suit :

1. Dans la barre de menus, cliquez sur **Gérer** &gt; **Accès (IAM)** puis sélectionnez **ID de service**.
2. Sélectionnez l'ID de service pour laquelle vous souhaitez affecter une règle de service.
3. Cliquez sur **Règles d'accès**.
4. Cliquez sur **Affecter un accès**.
5. Sélectionnez **Assign by resource**.
6. Sélectionnez un service.
7. Sélectionnez **Toutes les régions en cours** ou une région spécifique, si vous êtes invité à le faire.
8. Sélectionnez **Toutes les instances de service en cours** ou une instance de service spécifique.
9. Selon le service que vous avez sélectionné, les zones suivantes peuvent s'afficher. Si vous n'entrez aucune valeur dans ces zones, la règle est affectée au niveau instance de service et non au niveau compartiment.
    * **Type de ressource** : entrez **compartiment**.
    * **ID de ressource** : entrez le nom de votre compartiment
10. Sélectionnez toute combinaison de rôles pour affecter l'accès voulu à l'utilisateur.
11. Sélectionnez **Affecter**.

Pour accorder un accès à des services de gestion de compte individuels ou à tous ces services, procédez comme suit :

1. Dans la barre de menus, cliquez sur **Gérer** &gt; **Accès (IAM)** puis sélectionnez **ID de service**.
2. Sélectionnez l'ID de service pour laquelle vous souhaitez affecter une règle de service.
3. Cliquez sur **Règles d'accès**.
4. Cliquez sur **Affecter un accès**.
5. Sélectionnez d'affecter l'accès aux **Services de gestion des comptes**
6. Sélectionnez **Tous les services de gestion des comptes** ou bien un service de gestion de compte spécifique.
7. Sélectionnez toute combinaison de rôles pour affecter l'accès voulu.

Un message peut s'afficher indiquant qu'il existe une règle s'appliquant aux éléments sélectionnés. Si une règle incluant exactement les même rôles et les mêmes détails est créée, vous êtes invité à modifier la nouvelle règle car il n'est pas autorisé d'avoir des règles en double. Si vous créez une règle ayant les mêmes détails qu'une règle existante mais différentes affectations de rôle, vous êtes invité à consulter et mettre à jour la règle existante en incluant les affectations de rôle souhaitées.
{: tip}

## Edition d'un accès existant
{: #access_edit}

Pour éditer une règle existante :

1. Dans la barre de menus, cliquez sur **Gérer** &gt; **Accès (IAM)** puis sélectionnez **ID de service**.
2. Sélectionnez l'ID de service pour laquelle vous souhaitez éditer une règle de service.
3. Cliquez sur **Règles d'accès**.
4. Identifiez la ligne correspondant à la règle à éditer puis sélectionnez l'option permettant d'éditer la règle**** dans le menu **Actions** ![Icône Liste des actions](../icons/action-menu-icon.svg).
5. Apportez vos modifications, puis sauvegardez la règle.

Pour mettre à jour une règle de service en utilisant l'interface CLI, vous pouvez utiliser la commande [ibmcloud iam service-policy-update](/docs/cli/reference/ibmcloud?topic=cloud-cli-ibmcloud_commands_iam#ibmcloud_iam_service_policy_update).
```
ibmcloud iam service-policy-update SERVICE_ID POLICY_ID [-v, --version VERSION] {--file JSON_FILE | [-r, --roles ROLE_NAME1,ROLE_NAME2...] [--service-name SERVICE_NAME] [--service-instance SERVICE_INSTANCE] [--region REGION] [--resource-type RESOURCE_TYPE] [--resource RESOURCE] [--resource-group-name RESOURCE_GROUP_NAME] [--resource-group-id RESOURCE_GROUP_ID]} [-f, --force]",
```
{: codeblock}

Lorsque vous modifiez l'accès pour un ID de service, un message peut s'afficher indiquant que les règles en double ne sont pas autorisées. Si vous éditez une règle existante et que les modifications effectuées entrent en conflit avec l'accès déjà affecté, vous pouvez choisir de changer la règle en cours d'édition pour offrir un autre accès ou accéder à la règle existante en conflit afin d'effectuer les modifications nécessaires. Vous pouvez également supprimer la règle en cours d'édition s'il existe une règle identique répondant à vos besoins.
{: tip}

## Retrait de l'accès
{: #access_remove}

Pour retirer une règle existante :

1. Dans la barre de menus, cliquez sur **Gérer** &gt; **Accès (IAM)** puis sélectionnez **ID de service**.
2. Sélectionnez l'ID de service pour laquelle vous souhaitez supprimer une règle de service.
3. Cliquez sur **Règles d'accès**.
4. Identifiez la ligne contenant la règle à supprimer puis sélectionnez **Retirer** dans le menu **Actions** ![Icône Liste des actions](../icons/action-menu-icon.svg).
5. Consultez les détails relatifs à la règle que vous êtes sur le point de retirer, puis cliquez sur **Retirer** pour confirmer.

Pour supprimer une règle de service à l'aide de l'interface CLI, vous pouvez utiliser la commande [ibmcloud iam service-policy-delete](/docs/cli/reference/ibmcloud?topic=cloud-cli-ibmcloud_commands_iam#ibmcloud_iam_service_policy_delete).
```
ibmcloud iam service-policy-delete SERVICE_ID POLICY_ID [-f, --force]
```
{: codeblock}
