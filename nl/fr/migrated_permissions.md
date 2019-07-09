---

copyright:

  years: 2019

lastupdated: "2019-06-24"

keywords: migrated permissions, SoftLayer account permissions, migrated permission access group, migrated classic infrastructure permissions

subcollection: iam

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:important: .important}
{:new_window: target="_blank"}
{:note: .note}


# Gestion des droits de compte SoftLayer migrés
{: #migrated_permissions}

Vous pouvez utiliser des groupes d'accès de droits migrés pour gérer un ensemble de droits d'infrastructure classique (Softlayer) pour la gestion des informations de facturation et l'utilisation des cas de support. Les groupes d'accès contiennent un ensemble d'utilisateurs et d'ID de service qui disposent du même accès. Les utilisateurs de votre compte SoftLayer auxquels les droits de compte et de support ont été précédemment affectés sont désormais affectés au groupe d'accès des droits migrés respectifs. Par conséquent, les droits peuvent être directement gérés en utilisant des règles d'accès IAM.
{:shortdesc}

Ces groupes d'accès spéciaux incluent toutes les règles IAM appropriées pour conserver le comportement d'origine des droits de compte SoftLayer. Par exemple, pour qu'un utilisateur continue de voir toutes les mises à jour apportées à un cas de support par tous les utilisateurs, les groupes d'accès de droits migrés pour les droits de compte SoftLayer de demande de service incluent une règle IAM supplémentaire concernant le service Gestion des utilisateurs avec le rôle Afficheur affecté. Pour plus d'informations, voir [Attribution d'accès utilisateur pour l'utilisation de cas de support](/docs/get-support?topic=get-support-access#access).

Une fois que les droits d'infrastructure classique sont migrés, vous devez arrêter de les utiliser ainsi que l'interface CLI SoftLayer ou ue API pour les gérer. Consultez le tableau suivant présentant les droits d'infrastructure classique faisant désormais partie des groupes d'accès IAM. Les groupes d'accès sont créés uniquement pour les droits qui sont déjà affectés aux utilisateurs. Il est donc possible que vous voyiez un sous-ensemble des groupes d'accès qui figurent dans votre compte répertoriés dans le tableau ci-après.
{: note}

Vous pouvez continuer à gérer ces droits d'infrastructure classique migrés pour les utilisateurs directement via IAM en les ajoutant et en les retirant des groupes d'accès. Les règle de groupe d'accès sont verrouillées afin de conserver le comportement d'accès pour leurs membres. Toutefois, vous pouvez trouver utile de créer de nouveaux groupes d'accès qui incluent plusieurs règles d'accès pour les [services de gestion de compte](/docs/iam?topic=iam-account-services#account-services). Le tableau ci-après présente en détail une règle d'accès IAM qui inclut les droits du groupe d'accès des droits migrés de manière à ce que vous puissiez re-créer et même combiner ces droits à d'autres dans un nouveau groupe d'accès.

| Nom du groupe d'accès de droits migrés | Description | Service de gestion des comptes | Rôle IAM |
|-----------------------------------|-------------|-----------------------------------------|----------|
| Afficher le récapitulatif de compte | Afficher la page récapitulative de compte ainsi que les factures et les paiements.  |  Facturation |  Afficheur    |
| Obtenir les rapports de conformité | Demander des rapports de conformité. | Facturation |    Afficheur |
| Editer le profil de société | Editer les informations de profil de société. | Facturation  | Opérateur |
| Mettre à jour les détails de paiement | Mettre à jour les informations relatives au paiement mensuel. | Facturation   | Opérateur |
| Limiter les restrictions de cas de support de l'Union européenne | Activer ou désactiver l'option Support dans l'Union européenne qui restreint les données de cas de support à l'Union européenne.  |   Facturation |   Opérateur   |
| Ajouter des cas de support et afficher les commandes | Créer des cas de support et voir toutes les commandes.  | Centre de support |   Editeur   |
| Editer les cas de support | Editer les cas de support. | Centre de support |   Editeur |
| Rechercher des cas de support | Rechercher tous les cas de support si le droit d'affichage de cas est également affecté. | Centre de support |  Afficheur |
| Afficher les cas de support | Afficher tous les cas de support. | Centre de support et gestion des utilisateurs | Afficheur, Afficheur |
{: caption="Tableau 1. Droits d'infrastructure migrés qui sont mappés à des rôles IAM" caption-side="top"}

Pour l'accès Afficher les cas, créez deux règles distinctes avec le rôle Afficheur pour les services Centre de support et Gestion des utilisateurs. La règle sur le service Gestion des utilisateurs garantir que l'utilisateur peut voir tous les cas dans le compte quelle que soit la personne qui les a ouverts. En l'absence de règle sur le service Gestion des utilisateurs, si le propriétaire de compte a restreint la possibilité pour les utilisateurs d'afficher d'autres utilisateurs du compte, la vue de cas de l'utilisateur peut être limitée uniquement à ceux qu'il a ouverts.
{: note}

## Affectation de nouvelles règles d'accès IAM pour les droits migrés
{: #migrated-permissions-iam}

Pour recréer les droits migrés qui sont disponibles dans chaque groupe d'accès, vous pouvez affecter des règles à des utilisateurs individuels ou créer de nouveaux groupes d'accès dans votre compte. L'avantage de créer un nouveau groupe d'accès est que vous pouvez choisir de combiner un ensemble de droits pour un groupe d'accès au lieu de gérer un ensemble de groupes d'accès dont la portée est granulaire. Dans le cadre de cet exemple, les étapes décrivent comment créer un nouveau groupe d'accès et affecter une règle d'accès équivalente pour l'affichage du récapitulatif de compte et la consultation de tous les cas de support.

Lors de la récréation de ces droits par l'affectation de nouvelles règles d'accès IAM pour les services de gestion de compte, il est possible d'inclure des droits en plus du droit unique disponible dans le groupe d'accès de droits migrés. Par exemple, si vous affectez à un utilisateur le rôle Afficheur sur le service Facturation, cet utilisateur peut faire bien plus qu'afficher le récapitulatif de compte. Pour obtenir la liste intégrale de toutes les actions autorisées pour chaque rôle, voir [Affectation de l'accès aux services de gestion de compte](/docs/iam?topic=iam-account-services#account-services).
{: important}

Pour créer un groupe d'accès, procédez comme suit :

1. Dans la barre de menus, cliquez sur **Gérer** &gt; **Accès (IAM)** puis sélectionnez **Groupes d'accès**.
2. Cliquez sur **Créer**.
3. Entrez un nom et une description facultative pour votre groupe, puis cliquez sur **Créer**.
4. Cliquez sur **Ajouter des utilisateurs** sur l'onglet **Utilisateurs**.
3. Sélectionnez dans la liste les utilisateurs que vous souhaitez ajouter, puis cliquez sur **Ajouter au groupe**. Vous pouvez effectuer la même action depuis l'onglet **Identificateurs de service** si vous voulez ajouter des identificateurs de service au groupe.

Après avoir configuré votre groupe avec des utilisateurs et des ID de service, affectez un accès au groupe. N'oubliez pas que les règles que vous définissez pour le groupe s'appliquent à tous les membres qu'il contient.

1. Cliquez sur l'onglet **Règles d'accès**.
2. Cliquez sur **Affecter un accès**.
3. Sélectionnez l'option **Affecter l'accès aux services de gestion des comptes**.
4. Sélectionnez le service **Facturation**.
5. Sélectionnez le rôle **Afficheur**.
6. Cliquez sur **Affecter**.
7. Cliquez sur **Affecter un accès** pour affecter une seconde règle d'accès permettant d'afficher les cas de support.
8. Choisissez **Affecter l'accès aux services de gestion des comptes**.
9. Sélectionnez le service **Centre de support**.
10. Sélectionnez le rôle **Afficheur**.
11. Cliquez sur **Affecter**.
12. Cliquez sur **Affecter un accès** pour affecter une troisième règle d'accès permettant d'afficher tous les cas de support, quelle que soit la manière dont le propriétaire de compte a défini le paramètre de visibilité de l'utilisateur du compte.
13. Sélectionnez l'option **Affecter l'accès aux services de gestion des comptes**.
14. Sélectionnez le service **Gestion des utilisateurs**.
15. Sélectionnez le rôle **Afficheur**.
16. Cliquez sur **Affecter**.

Trois règles sont maintenant affectées à votre groupe :

* Un règle pour l'affichage du récapitulatif de compte et toutes les autres actions qui sont associées au rôle Afficheur dans le service Facturation.
* Un règle pour l'affichage et la recherche de cas de support dans le compte.
* Un règle pour l'affichage de tous les utilisateurs dans le compte et toutes les autres actions qui son associées au rôle Afficheur dans le service Gestion des utilisateurs.

