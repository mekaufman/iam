---

copyright:

  years: 2019

lastupdated: "2019-07-24"

keywords: enterprise policy, enterprise access, assign enterprise access, enterprise service

subcollection: iam

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:tip: .tip}
{:note: .note}
{:external: target="_blank" .external}

# Affectation de l'accès d'entreprise
{: #assign-access-enterprise}

Pour affecter à un utilisateur l'accès lui permettant de gérer une entreprise {{site.data.keyword.Bluemix}}, vous devez l'inviter à rejoindre le compte d'entreprise et lui affecter l'accès au service de gestion des comptes Entreprise.
{:shortdesc}

Pour pouvoir gérer l'[entreprise](/docs/account?topic=account-enterprise), une règle d'accès est requise dans le compte d'entreprise. Lorsque vous affectez une règle de service de gestion des comptes Entreprise à un utilisateur dans un compte enfant d'une entreprise, l'utilisateur ne peut pas gérer l'entreprise à laquelle le compte appartient. En fonction du rôle affecté de l'utilisateur pour le service de gestion des comptes Entreprise, l'utilisateur peut effectuer des actions spécifiques :

* Créer des comptes dans l'entreprise
* Créer et nommer des groupes de comptes
* Déplacer des comptes dans des groupes de comptes
* Importer des comptes existants dans l'entreprise
* Mettre à jour le domaine ou le nom de l'entreprise
* Afficher les rapports d'utilisation pour l'entreprise, un groupe de comptes spécifique et ses groupes de comptes ou les comptes qui s'y trouvent ou un compte spécifique

Une règle accordant à un utilisateur l'accès au service d'entreprise peut être affectée pour l'ensemble de l'entreprise ou uniquement pour un groupe de comptes ou un seul compte spécifique.
{: tip}

Généralement, le compte d'entreprise lui-même ne contient pas beaucoup de ressources. A la place, les ressources sont créées dans les comptes enfant de l'entreprise. Les utilisateurs peuvent être invités à rejoindre ces comptes et l'accès permettant de gérer et d'utiliser ces ressources peut leur être accordé. L'accès et l'appartenance à un compte d'entreprise ne s'appliquent pas aux groupes de comptes et aux comptes enfant de la hiérarchie de l'entreprise. La gestion des utilisateurs ainsi que la gestion des accès sont spécifiques à chaque compte, comme cela est décrit dans les diagrammes suivants.

Le premier diagramme présente comment vous pouvez affecter une règle à un utilisateur dans le compte d'entreprise afin de gérer l'ensemble de l'entreprise ou une règle s'appliquant à un groupe de comptes. Dans le dernier cas, vous disposez d'un accès permettant de gérer uniquement ce groupe de comptes et les autres groupes de comptes ou les comptes enfant de ce groupe. 

![Accès de l'entreprise](images/enterprise-access.svg "Les utilisateurs de l'entreprise disposent de l'accès leur permettant de gérer uniquement les entités de l'entreprise")

La cible et le rôle de la règle sont importants pour la détermination de la portée de l'accès. Un utilisateur, un ID de service ou un groupe d'accès d'entreprise à laquelle la règle s'applique peut effectuer des tâches de gestion dans l'ensemble de l'entreprise, dans un groupe de comptes pouvant contenir d'autres groupes de comptes et comptes ou même dans un seul compte. Par exemple, si vous affectez à un utilisateur du compte d'entreprise une règle d'accès sur le service de gestion des comptes Entreprise avec une cible s'appliquant à un groupe de comptes spécifique, cet utilisateur dispose d'un accès lui permettant d'effectuer des tâches dans le groupe de comptes. L'utilisateur ne peut pas effectuer d'actions affectant l'entreprise dans son ensemble (mettre à jour le nom de l'entreprise ou le document, par exemple) lorsque la cible s'applique à un compte ou un groupe de comptes spécifique.

Vous pouvez affecter aux utilisateurs d'un compte enfant au sein de l'entreprise des règles d'accès qui s'appliquent à la gestion de ce compte uniquement ou des ressources qu'il contient. Si vous affectez à un utilisateur d'un compte enfant un rôle sur le service de gestion des comptes Entreprise, par exemple, l'utilisateur ne peut pas effectuer d'actions au niveau du compte d'entreprise. Vous devez l'ajouter à ce compte et affecter la règle dans ce contexte.

![Accès aux comptes](images/account-access.svg "Les utilisateurs de compte enfant ont accès à leur compte uniquement et non au reste de l'entreprise")

## Règles requises pour des travaux spécifiques
{: #sample-enterprise-policies}

En fonction de la tâche à effectuer, plusieurs règles d'accès peuvent être requises pour un utilisateur qui n'est pas propriétaire de l'entreprise. Les exemples suivants présentent l'ensemble de règles d'accès que vous devez affecter à un utilisateur de l'entreprise afin qu'il puisse effectuer des tâches spécifiques.

Si vous êtes propriétaire d'un compte qui ne fait partie d'aucune entreprise mais que vous souhaitez qu'un autre utilisateur de votre compte puisse convertir ce dernier en entreprise, vous pouvez affecter à cet utilisateur le rôle Administrateur sur le service de gestion des comptes Facturation.
{: note}

### Affichage de l'utilisation et gestion de la facturation dans l'entreprise
{: #billing-admin-enterprise}

Pour qu'un utilisateur puisse [afficher les rapports d'utilisation](/docs/billing-usage?topic=billing-usage-enterprise-usage) de tous les comptes de l'entreprise, effectuer des paiements et consulter les factures, vous devez lui attribuer toutes les règles d'accès suivantes :

* Rôle d'afficheur des rapports d'utilisation pour le service de gestion des comptes Entreprise dans le compte d'entreprise
* Rôle Administrateur pour le service de gestion des comptes Facturation dans le compte d'entreprise

### Importation d'un compte existant dans l'entreprise
{: #add-account}

Pour qu'un utilisateur puisse [importer un compte IBM Cloud existant dans l'entreprise](/docs/account?topic=account-enterprise-add#add-accounts), vous devez affecter toutes les règles d'accès suivantes :

* Rôle Administrateur sur le service de gestion des comptes Facturation dans le compte à importer
* Rôle Administrateur ou Editeur sur le service de gestion des comptes Entreprise pour le groupe de comptes ou le compte d'entreprise auquel le compte sera ajouté
* Rôle Administrateur sur le service de gestion des comptes Facturation pour le compte d'entreprise

### Déplacement d'un compte
{: #move-accountgroup}

Pour qu'un utilisateur puisse [déplacer un compte dans une entreprise](/docs/account?topic=account-enterprise-organize#move-accounts), vous devez affecter les règles d'accès suivantes :

* Rôle Administrateur pour le service de gestion des comptes Facturation dans le compte d'entreprise

Puis une des deux options suivantes :

* Rôle Administrateur ou Editeur pour le service de gestion des comptes Entreprise pour l'ensemble de l'entreprise
* Rôle Administrateur ou Editeur sur le groupe de comptes actuel et cible où ce compte sera déplacé

Pour savoir quelles actions les utilisateurs peuvent effectuer pour chaque rôle, voir [Actions et rôles pour les services de gestion des comptes](/docs/iam?topic=iam-account-services#account-management-actions-roles).

## Affectation de l'accès dans la console
{: #enterprise-access-console}

Pour affecter une règle d'accès à un utilisateur existant dans le compte d'entreprise, procédez comme suit :

Vous pouvez définir la cible de la règle afin qu'elle s'applique à l'ensemble de l'entreprise, à un groupe de comptes spécifique, qui peut inclure l'accès à tous les comptes s'y trouvant, ou même à un compte spécifique d'un groupe de comptes.
{: tip}

1. Dans la barre de menus, cliquez sur **Gérer** &gt; **Accès (IAM)** puis sélectionnez **Utilisateurs**.
2. Sur la ligne de l'utilisateur auquel vous souhaitez affecter l'accès, sélectionnez le menu **Actions** ![Icône Liste des actions](../icons/action-menu-icon.svg) puis cliquez sur **Affecter un accès**.
3. Choisissez d'affecter l'accès aux **Services de gestion des comptes**.
4. Sélectionnez **Entreprise** comme service.
5. Facultatif : Définissez l'application de la règle à l'entreprise, au groupe de comptes ou au compte.
6. Sélectionnez toute combinaison de rôles pour affecter l'accès voulu.

| Rôles | Actions |
|:-------|----------|
| Afficheur |  Affichage de l'entreprise, des groupes de comptes et des comptes    |
| Opérateur |  Affichage de l'entreprise, des groupes de comptes et des comptes    |
| Editeur |  Affichage et mise à jour de l'entreprise en éditant le nom et le domaine, création de comptes et de groupes de comptes, affichage des rapports d'utilisation et importation de comptes |
| Administrateur |  Affichage et mise à jour de l'entreprise en éditant le nom et le domaine, création de comptes et de groupes de comptes, déplacement de comptes entre différents groupes de comptes, importation de comptes existants et affichage des rapports d'utilisation  |
| Afficheur du rapport d'utilisation | Affichage de l'entreprise, de comptes et de groupes de comptes et affichage des rapports d'utilisation pour tous les comptes de l'entreprise |
{: caption="Tableau 1. Rôles et actions pour le service de gestion des comptes Entreprise" caption-side="top"}

## Affectation de l'accès à l'aide de l'interface de ligne de commande
{: #enterprise-cli-policy}

Pour créer une règle d'accès pour un utilisateur, exécutez la commande **`ibmcloud iam user-policy-create`**. Dans la commande exemple, un fichier JSON permet de spécifier les détails de la règle. Consultez l'exemple dans la section [Affectation de l'accès à l'aide de l'API](#enterprise-api-policy) pour connaître les éléments pouvant être inclus dans le fichier JSON.

Créer une règle utilisateur :
```
$ ibmcloud iam user-policy-create name@example.com -f policy.json
```

Pour plus d'informations, voir [ibmcloud iam user-policy-create](/docs/cli/reference/ibmcloud?topic=cloud-cli-ibmcloud_commands_iam#ibmcloud_iam_user_policy_create).

## Affectation de l'accès à l'aide de l'API
{: #enterprise-api-policy}

La demande exemple suivante affecte une règle pour un utilisateur ayant le rôle Editeur sur le service Entreprise d'un compte d'entreprise s'appliquant à un groupe de comptes. Ce type de règle est hiérarchique et s'applique à tous les objets descendants dans la hiérarchie, ce qui correspond à tous les groupes de comptes ou tous les comptes du groupe de comptes cible spécifié.  

```
curl -X POST \
'https://iam.cloud.ibm.com/v1/policies' \
-H 'Authorization: $TOKEN' \
-H 'Content-Type: application/json' \
-d '{
  "type": "access",
  "subjects": [
    {
      "attributes": [
        {
          "name": "iam_id",
          "value": "<IBMid-example>"
        }
      ]
    }
  ],
  "roles":[
    {
      "role_id": "crn:v1:bluemix:public:iam::::role:Editor"
    }
  ],
  "resources":[
    {
      "attributes": [
        {
          "name": "accountId",
          "value": "<account-id-example>"
        },
        {
          "name": "serviceName",
          "value": "enterprise"
        },
        {
          "name": "accountGroupId",
          "value": "<accountGroupId-example>"
        }
      ]
    }
  ]
}'
```
{: codeblock}

Pour plus d'informations, voir la section relative à la [création d'une règle](https://cloud.ibm.com/apidocs/iam-policy-management#create-a-policy){: external}.
