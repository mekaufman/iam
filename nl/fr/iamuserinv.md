---

copyright:

  years: 2015, 2019

lastupdated: "2019-08-08"

keywords: invite, invite users, invitation access, vpn-only user

subcollection: iam

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:tip: .tip}
{:note: .note}
{:external: target="_blank" .external}

# Invitation d'utilisateurs à rejoindre un compte
{: #iamuserinv}

Utilisez {{site.data.keyword.Bluemix}} Identity and Access Management (IAM) pour inviter des utilisateurs, annuler des invitations, et renvoyer une invitation en attente à un utilisateur invité. En outre, vous pouvez inviter un utilisateur unique ou plusieurs utilisateurs à la fois.
{:shortdesc}

Pour inviter des utilisateurs et gérer les invitations en attente, vous devez être propriétaire du compte, responsable de l'organisation, être un utilisateur disposant d'une règle d'accès IAM et ayant au moins le rôle Editeur pour le service de gestion des utilisateurs, ou vous devez avoir des droits d'infrastructure classique pour ajouter des utilisateurs.

## Configuration d'une invitation
{: #invitations}

Pour inviter des utilisateurs ou gérer les invitations d'utilisateur sur votre compte, procédez comme suit :

1. Dans la barre de menus, cliquez sur **Gérer** &gt; **Accès (IAM)** puis sélectionnez **Utilisateurs**.
2. Cliquez sur **Inviter des utilisateurs**.
3. Spécifiez l'adresse électronique de l'utilisateur. Si vous invitez plusieurs utilisateurs avec une même invitation, ils bénéficient tous du même droit d'accès.
4. Ajoutez une ou plusieurs options d'accès que vous gérez. Vous devez affecter au moins une option d'accès. Pour les options d'accès supplémentaires que vous n'ajoutez ou ne configurez pas, la valeur par défaut **Aucun accès** lui est affectée. L'une des options d'accès ou toutes les options suivantes peuvent s'afficher, selon celles que vous êtes autorisé à gérer :

  * **Services**
  * **Accès Cloud Foundry**
  * **Accès à l'infrastructure classique**.

  Pour plus d'informations, voir [Octroi d'un accès utilisateur](/docs/iam?topic=iam-iamuserinv#assignaccess).

Si vous déterminez qu'un utilisateur n'a pas besoin d'un accès, vous pouvez annuler l'invitation de n'importe quel utilisateur dont l'état indique En cours de traitement ou En attente dans la colonne Statut. Si un utilisateur invité n'a pas reçu d'invitation, vous pouvez renvoyer l'invitation à n'importe quel utilisateur dont l'état indique En attente.

### Invitation d'utilisateur via l'interface CLI
{: #cli-invite}

Pour inviter des utilisateurs via l'interface de ligne de commande (CLI), exécutez la commande suivante :

```
ibmcloud account user-invite USER_EMAIL [-o ORG [--org-role ORG_ROLE] [-s SPACE, --space-role SPACE_ROLE]]
```

L'utilisation de l'interface CLI permet de choisir d'affecter ou non l'accès à Cloud Foundry, ou encore de l'affecter ultérieurement. Pour plus d'informations sur les paramètres de commande, voir [**`ibmcloud account user-invite`**](/docs/cli/reference/ibmcloud?topic=cloud-cli-ibmcloud_commands_account#ibmcloud_account_user_invite). 

### Invitation d'utilisateur via API
{: #api-invite}

Vous pouvez utiliser l'[API](https://cloud.ibm.com/apidocs/user-management#invite-users){: external} pour inviter des utilisateurs en bloc. Tous les utilisateurs figurant dans une seule invitation reçoivent le même accès. Lorsque vous invitez des utilisateurs via l'API, vous entrez dans une liste les adresses e-mail séparées par des virgules, chaque entrée étant placée entre guillemets. Par exemple :


```
curl -X POST \
  https://user-management.cloud.ibm.com/v2/accounts/987d4cfd77b04e9b9e1a6asdcc861234/users \
  -H 'Authorization: Bearer <IAM_TOKEN>'
  -H 'Content-Type: application/json' \
    -d '{
      "users": [
      {
        "email": "cloud_api_example_member@ibm.com", "second_user@ibm.com", "third_user@ibm.com",
        "account_role": "Member"
      }],
      "iam_policy": [
      {
        "roles": [
        {
          "id": "crn:v1:bluemix:public:iam::::role:Viewer"
        }],
        "resources": [
        {
          "accountId": "111d4cfd77b04e9b9e1a6asdcc861234",
          "resourceType": "resource-group",
          "resource": "111449dd871049c29ec3a53853ce123e"
        }]
      }]
    }'
```
{: codeblock}

## Affectation de l'accès utilisateur à partir d'une invitation
{: #assignaccess}

Vous accordez un accès aux utilisateurs lorsque vous les invitez en leur affectant des règles {{site.data.keyword.Bluemix}} IAM, l'accès Cloud Foundry et des droits d'infrastructure classique. En fonction des options d'accès que vous êtes autorisé à gérer, vous pouvez inviter des utilisateurs et leur accorder des droits d'accès dans le compte, les groupes de ressources, les organisations, les espaces, les instances de service et l'infrastructure classique. Les sections suivantes décrivent les trois types d'accès que vous pouvez affecter à un utilisateur invité.

### Services
{: #invite_services}

Vous pouvez affecter un accès en créant une règle d'accès {{site.data.keyword.Bluemix_notm}} IAM initiale lorsque vous invitez un nouvel utilisateur. Dans la section Services, vous pouvez accorder un accès utilisateur à des services de gestion de compte, services se trouvant dans un groupe de ressources avec l'accès permettant de gérer le groupe de ressources ou une ressource individuelle du compte.

Une fois que l'utilisateur a accepté invitation, vous pouvez lui affecter des accès supplémentaires. Pour plus d'informations sur l'édition de règles afin d'ajouter des rôles supplémentaires, sur l'affectation d'accès supplémentaire ou sur le retrait d'une règle pour un utilisateur, voir [Gestion de l'accès aux ressources](/docs/iam?topic=iam-iammanidaccser#iammanidaccser).

Selon le service que vous sélectionnez lorsque vous affectez la règle, il se peut que les zones décrites dans les procédures suivantes ne soient pas toutes affichées.
{: note}

#### Accès aux services de gestion de compte
{: #invite_acct_mgmt}

Pour déléguer certaines de vos responsabilités en tant que propriétaire de compte, vous pouvez fournir un accès utilisateur aux services de gestion de compte. Par exemple, vous pouvez déléguer l'autorisation d'afficher les informations de facturation et d'utilisation, d'inviter et de supprimer des utilisateurs, de gérer des groupes d'accès ou de gérer des ID de service. Vous pouvez octroyer l'accès à tous les services de gestion de compte ou bien à un seul.

1. Dans la page Inviter des utilisateurs, développez la section Services.
2. Sélectionnez **Services de gestion des comptes** dans la liste **Affecter l'accès à**. 
3. Sélectionnez **Tous les services de gestion des comptes** ou bien un service de gestion de compte spécifique.
4. Sélectionnez toute combinaison de rôles pour affecter l'accès voulu.

#### Accès au groupe de ressources
{: #invite_rgs}

Vous pouvez accorder l'accès à tous les services d'un groupe de ressources ou à un seul type de service d'un groupe de ressources.

1. Dans la page Inviter des utilisateurs, développez la section Services.
2. Sélectionnez **Groupe de ressources** dans la liste **Affecter l'accès à**.
3. Sélectionnez un groupe de ressources.
4. Sélectionnez un rôle dans la liste **Affecter l'accès à un groupe de ressources** pour autoriser l'utilisateur à afficher le groupe de ressources dans la liste des ressources, à éditer le nom du groupe de ressources ou à gérer l'accès des utilisateurs au groupe. Vous pouvez sélectionner **Aucun accès**, si vous souhaitez que l'utilisateur puisse accéder uniquement à la ressource spécifiée et non au groupe auquel elle appartient.
5. Sélectionnez un service dans le groupe de ressources ou sélectionnez d'accorder l'accès à tous les services du groupe sélectionné.
6. Sélectionnez toute combinaison de rôles pour affecter l'accès voulu. Cet accès s'applique uniquement aux ressources sélectionnées pour la règle. Il n'accorde pas l'accès au conteneur que constitue le groupe de ressources.

#### Accès à la ressource
{: #invite_resources}

Vous pouvez accorder l'accès à une seule ressource de votre compte jusqu'au niveau instance.

1. Dans la page Inviter des utilisateurs, développez la section Services.
2. Sélectionnez **Ressource** dans la liste **Affecter l'accès à**. 
3. Sélectionnez un service.
4. Sélectionnez **Toutes les régions en cours** ou une région spécifique, si vous êtes invité à le faire.
5. Sélectionnez **Toutes les instances de service en cours** ou une instance de service spécifique.
6. Selon le service que vous avez sélectionné, les zones suivantes peuvent s'afficher. Si vous n'entrez pas de valeurs pour ces zones, la règle est affectée au niveau instance de service et au niveau compartiment.
    * **Type de ressource** : entrez `compartiment`.
    * **ID de ressource** : entrez le nom de votre compartiment
7. Sélectionnez toute combinaison de rôles pour affecter l'accès voulu.

Pour plus d'informations sur les rôles utilisés lors de l'affectation de l'accès, voir [Accès IAM](/docs/iam?topic=iam-userroles#iamusermanrol).

### Accès Cloud Foundry
{: #invite_cf}

Lorsque vous invitez de nouveaux utilisateurs, vous pouvez choisir d'ajouter l'utilisateur à une organisation dans le compte. Si vous ajoutez l'utilisateur à une organisation, vous pouvez lui attribuer un rôle dans l'organisation. Vous pouvez ensuite accorder à l'utilisateur invité un accès à n'importe quel espace (voire à tous) dans l'organisation sélectionnée, avec le rôle d'espace qui lui est affecté.

1. Dans la page Inviter des utilisateurs, développez la section Accès Cloud Foundry.
2. Sélectionnez une organisation à laquelle ajouter l'utilisateur.
3. Sélectionnez un rôle d'organisation afin de définir le niveau d'accès pour l'organisation sélectionnée.
4. Facultatif : cliquez sur **Ajouter un rôle d'organisation** pour spécifier un rôle supplémentaire.
5. Sélectionnez **Toutes les régions en cours** ou une région spécifique.
6. Sélectionnez **Tous les espaces en cours** ou un espace spécifique.
7. Sélectionnez un rôle d'espace afin de définir un niveau d'accès pour les espaces sélectionnés.
8. Facultatif : cliquez sur **Ajouter un rôle d'espace** pour spécifier un rôle supplémentaire.

Pour plus d'informations sur les rôles utilisés lors de l'affectation de l'accès, voir [Rôles Cloud Foundry](/docs/iam?topic=iam-cfaccess#cfroles).

Vous pouvez ajouter un rôle Cloud Foundry à l'aide de la commande de l'interface de ligne de commande [**`ibmcloud account user-invite`**](/docs/cli/reference/ibmcloud?topic=cloud-cli-ibmcloud_commands_account#ibmcloud_account_user_invite), mais vous devez utiliser la console pour lui accorder d'autres accès ou autorisations.
{: tip}

### Accès à l'infrastructure classique
{: #invite_classicinfra}

Les droits accordés sont limités automatiquement au sous-ensemble de droits dont vous disposez. Vous devenez l'utilisateur parent de tout utilisateur que vous invitez.

1. Dans la page Inviter des utilisateurs, développez la section Accès à l'infrastructure classique.
2. Sélectionnez un ensemble de droits pour affecter des droits en bloc prédéfinis.

L'accès aux périphériques est accordé séparément après l'ajout de l'utilisateur. Accédez à l'option d'accès **Infrastructure classique** pour un utilisateur de la console.
{: note}

Pour plus d'informations sur la configuration des droits d'accès pour les utilisateurs une fois qu'ils ont été ajoutés à votre compte, voir [Gestion de l'accès à l'infrastructure classique](/docs/iam?topic=iam-mngclassicinfra#mngclassicinfra).

## Ajout d'utilisateurs VPN uniquement
{: #add-vpn-only}

En tant que propriétaire de compte ou qu'utilisateur disposant de droits de gestion d'infrastructure classique d'utilisateur, vous pouvez ajouter un utilisateur VPN uniquement.

1. Sur la page Utilisateurs, cliquez sur **Ajouter un utilisateur VPN uniquement**.
2. Entrez les détails des informations personnelles de l'utilisateur.
3. Cliquez sur **Sauvegarder**.
