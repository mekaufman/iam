---



copyright:

  years: 2018, 2019

lastupdated: "2019-01-30"

keywords: frequently asked question, faq

subcollection: iam

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:tip: .tip}
{:faq: data-hd-content-type='faq'}
{:note: .note}

# Foire aux questions
{: #iamfaq}

## En quoi consiste l'application {{site.data.keyword.cloud_notm}} Identity and Access Management ?
{: #whatisiam}
{: faq}

Identity and Access Management (IAM) vous permet d'authentifier de manière sécurisée les utilisateurs des services de plateforme et de contrôler l'accès aux ressources à travers la plateforme {{site.data.keyword.cloud_notm}}. Un ensemble de services IBM Cloud est activé afin d'utiliser Cloud IAM pour le contrôle d'accès. Ils sont organisés en groupes de ressources au sein de votre compte pour permettre aux utilisateurs un accès rapide et facile à plusieurs ressources à la fois. Des règles d'accès Cloud IAM permettent d'affecter à des ID utilisateur et de service un accès aux ressources de votre compte. Pour plus d'informations, voir [{{site.data.keyword.cloud_notm}} Identity and Access Management](/docs/iam?topic=iam-iamoverview#iamoverview).

## Qu'est-ce qu'un service activé pour IAM ?
{: #iam-enabled}
{: faq}

Un service activé pour IAM doit résider dans un groupe de ressources et l'accès au service est accordé via les règles d'accès IAM. Lorsque vous créez un service activé pour IAM depuis le catalogue, vous devez l'affecter à un groupe de ressources. Pour plus d'informations, voir [Qu'est-ce qu'une ressource ?](/docs/resources?topic=resources-resource#resource)

{{site.data.keyword.containerlong_notm}} est la seule exception ; il est contrôlé par IAM, mais est toujours affecté au groupe de ressources par défaut. Par conséquent, vous ne disposez pas d'une autre option lorsque vous le créez depuis le catalogue. D'autre part, il ne peut pas être affecté à un autre groupe de ressources.


## IAM et Cloud Foundry sont-ils associés ?
{: #iam-cloudfoundry}
{: faq}

Ils ne sont pas associés. Cloud Foundry est une plateforme open source qui utilise des organisations, des espaces et des rôles Cloud Foundry pour gestion des accès. IAM est la méthode sécurisée pour authentifier les utilisateurs pour les services de la plateforme et le contrôle d'accès aux ressources à travers la plateforme {{site.data.keyword.cloud_notm}} à l'aide de groupes de ressources et de rôles d'accès IAM.

Leurs systèmes de gestion des accès sont complètement différents. Les ressources IAM appartiennent à un groupe de ressources tandis que les ressources Cloud Foundry appartiennent à une organisation et à un espace. Les règles d'accès IAM sont utilisées pour attribuer un accès aux ressources dans un groupe de ressources. Les rôles d'organisation et d'espace Cloud Foundry sont utilisés pour attribuer aux utilisateurs un accès aux ressources Cloud Foundry dans un espace. IAM ne vous accorde aucun accès dans les espaces Cloud Foundry et les rôles Cloud Foundry ne vous accordent pas d'accès à des ressources dans un groupe de ressources.

## Comment puis-je vérifier les accès qui me sont octroyés ?
{: #iam-access}
{: faq}

Accédez à **Gérer** &gt; **Accès (IAM)** puis sélectionnez votre nom sur la page Utilisateurs. Ensuite, selon l'accès recherché, ouvrez les différents onglets :

* Pour déterminer l'accès dont vous disposez dans les groupes d'accès auxquels vous êtes affecté, sélectionnez **Groupes d'accès**.
* Pour voir les règles d'accès IAM qui vous sont affectées, sélectionnez l'option **Règles d'accès**.
* Pour voir votre accès Cloud Foundry pour toutes les organisations et tous les espaces, sélectionnez **Accès Cloud Foundry**.


## Comment demander l'accès à une ressource ?
{: #request-access}
{: faq}

Le propriétaire du compte peut mettre à jour l'accès à n'importe quelle ressource du compte ou vous pouvez contacter un utilisateur affecté au rôle administrateur sur le service ou l'instance de service.

## Pourquoi dois-je utiliser des groupes de ressources et des groupes d'accès ?
{: #resource-groups}
{: faq}

Un groupe de ressources est un conteneur logique de ressources. Lorsqu'une ressource est créée, elle est affectée à un groupe de ressources et ne peut dès lors pas être déplacée.

Un groupe d'accès est utilisé pour organiser facilement un ensemble d'utilisateurs et d'ID de service dans une même entité afin de faciliter les affectations d'accès. Vous pouvez affecter une règle unique à un groupe d'accès afin d'octroyer à ses membres ces autorisations. Si vous avez plusieurs utilisateurs ou ID de service nécessitant le même accès, créez un groupe d'accès au lieu d'octroyer individuellement et successivement l'accès à chaque utilisateur ou ID de service concerné.

En utilisant à la fois des groupes de ressources et des groupes d'accès, vous pouvez rationaliser la procédure d'affectation d'accès en affectant un nombre limité de règles. Vous pouvez organiser toutes les ressources auxquelles a besoin d'accéder un groupe spécifique d'utilisateurs et d'ID de service en constituant un groupe d'accès, puis en affectant une seule règle octroyant l'accès à toutes les ressources du groupe de ressources.

Pour plus d'informations, voir [Meilleures pratiques pour l'affectation d'accès](/docs/iam?topic=iam-account_setup#account_setup).

## Comment m'assurer que mes utilisateurs puissent créer des ressources au sein d'un groupe de ressources ?
{: #resources}
{: faq}

Pour créer une ressource dans un groupe de ressources, l'utilisateur doit disposer de deux règles d'accès : une affecté au groupe de ressources lui-même, l'autre affectés aux ressources dans le groupe. L'accès au groupe de ressources lui-même est simplement l'accès au conteneur qui organise les ressources et ce type de règle autorise un utilisateur à afficher, éditer ou gérer l'accès au groupe, mais non pas aux ressources qu'il héberge. L'accès aux services dans le groupe de ressources permet à l'utilisateur de travailler avec les instances de service, ce qui indique que l'utilisateur peut en créer une.

Ainsi, l'utilisateur doit disposer au minimum de l'accès suivant :

* Rôle Afficheur ou supérieur sur le groupe de ressources lui-même
* Rôle Editeur ou supérieur sur le service ou sur tous les services du groupe de ressources


## De quel accès ai-je besoin pour accorder un accès à d'autres utilisateurs ?
{: #user-access}
{: faq}

Concernant les services activés par IAM, vous devez disposer du rôle Administrateur pour le service ou la ressource auxquels vous désirez accorder l'accès à d'autres utilisateurs. Si vous souhaitez affecter l'accès à tous les services ou ressources du compte, vous avez besoin d'une règle s'appliquant à tous les services activés pour Identity and Access avec le rôle Administrateur. Pour affecter l'accès aux services de gestion de compte pour les utilisateurs, vous devez disposer du rôle Administrateur pour le service spécifique ou tous les services de gestion de compte.

Concernant les services Cloud Foundry, vous devez disposer des rôles de gestionnaire d'espace et d'organisation Cloud Foundry pour accorder l'accès aux ressources Cloud Foundry.

Concernant l'infrastructure classique, vous devez disposer du droit de gestion d'infrastructure classique d'utilisateur ainsi que des droits de catégorie de service et d'unité pour les ressources auxquelles vous souhaitez que l'utilisateur ait accès.

## Quelle est la différence entre l'octroi d'un accès pour gérer un groupe de ressources par rapport à l'accès aux ressources dans un groupe de ressources ?
{: #providing-access}
{: faq}

Lorsqu'un accès pour gérer un groupe de ressources vous est octroyé, vous pouvez afficher, modifier le nom et gérer l'accès au groupe de ressources lui-même en fonction du rôle assigné. L'accès à un groupe de ressources lui-même n'accorde pas à un utilisateur l'accès aux ressources dans le groupe.

Lorsque vous avez accès à des ressources d'un groupe de ressources, vous pouvez modifier, supprimer, et créer des instances, ou effectuer toutes les actions de gestion pour les services spécifiés dans le groupe de ressources en fonction du rôle affecté.

Par exemple, pour les rôles de gestion de plateforme et les actions de services de gestion de compte, voir le [tableau des rôles de plateforme](/docs/iam?topic=iam-userroles#platformrolestable2).

## Qui est habilité à supprimer des utilisateurs ?
{: #remove-users}
{: faq}

Le propriétaire du compte peut retirer des utilisateurs du compte, et tout utilisateur ayant l'accès suivant peut retirer des utilisateurs d'un compte :

* Règle IAM pour le service de gestion des comptes utilisateur avec le rôle Administrateur affecté. Vous devez être gestionnaire d'organisation Cloud Foundry si l'utilisateur appartient à une organisation Cloud Foundry.
* Si vous avez une infrastructure classique dans votre compte, un utilisateur doit avoir une règle IAM pour le service de gestion de compte utilisateur avec le rôle Administrateur affecté. Vous devez être gestionnaire d'organisation Cloud Foundry si l'utilisateur appartient à une organisation Cloud Foundry et être un ancêtre de l'utilisateur dans la hiérarchie d'utilisateurs de l'infrastructure classique avec le droit de gestion correspondant affecté.

## Comment puis-je me procurer l'authentification multi-facteur avec IBMid pour mon compte ?
{: #multi-factor}
{: faq}

1. Accédez à **Gérer** &gt; **Accès (IAM)** puis sélectionnez **Paramètres**.
2. Choisissez **Authentification multi-facteur** puis cliquez sur **Oui, je suis sûr**. Pour plus d'informations, voir [Exigence de l'authentification multi-facteur pour les utilisateurs de votre compte](/docs/iam?topic=iam-enablemfa#enablemfa).

## Quelle est la différence entre rôles de service et de plateforme ?
{: #service-platform-roles}
{: faq}

Les rôles de service et de plateforme sont deux types de rôles différents :

* Les rôles de plateforme indiquent comment utiliser un service avec un compte, par exemple comment créer des instances, lier des instances et gérer l'accès de l'utilisateur au service. Pour les services de plateforme, ces rôles permettent aux utilisateurs de créer des groupes de ressources et de gérer les ID de service, par exemple. Les rôles de plateforme sont les suivants : administrateur, éditeur, opérateur et afficheur.

* Rôles de service définissent la possibilité d'effectuer des actions sur un service et sont spécifiques à chaque service (par exemple, les appels d'API ou l'accès à l'interface utilisateur). Les rôles de service sont les suivants : responsable, auteur et lecteur. Pour plus d'informations sur la façon dont ces rôles s'appliquent, reportez-vous à la documentation du service spécifique.

## Quelle est la différence entre un groupe de ressources et les organisations et espaces Cloud Foundry ?
{: #groups-organizations}
{: faq}

Au début de {{site.data.keyword.Bluemix_notm}}, un service de plateforme open source pour le contrôle d'accès et l'organisation de ressources dénommée Cloud Foundry constituait l'unique méthode d'organisation et de contrôle d'accès aux ressources. Avec l'expansion d'{{site.data.keyword.Bluemix_notm}}, une nouvelle méthode pouvant être utilisée par tous les types de services et de ressources s'avérait nécessaire. Des groupes de ressources sont dorénavant utilisés pour regrouper et organiser de nombreux types de ressources et IAM est utilisé pour contrôle cohérent de l'accès aux services et aux ressources. Un certain nombre de services ont déjà adopté l'utilisation de groupes de ressources et d'IAM, d'autres passeront au fil du temps à la nouvelle méthode d'organisation des ressources et de contrôle d'accès.

Le contrôle d'accès et l'organisation des ressources du compte sont les principales différences entre les groupes de ressources et les organisations et espaces Cloud Foundry. Les groupes de ressources organisent les services activés pour IAM dans un compte dont l'accès est contrôlé via des règles IAM. Les organisations et les espaces sont gérés à l'aide de rôles Cloud Foundry pour le contrôle d'accès et les ressources Cloud Foundry sont affectées à des espaces. Vous ne pouvez utiliser des organisations et des espaces pour organiser et gérer l'accès aux ressources que dans le domaine Cloud Foundry, tandis que les groupes de ressources et IAM peuvent être utilisés pour de multiples types de ressources à travers {{site.data.keyword.Bluemix_notm}}.

## Comment déléguer les fonctions d'administrateur de compte ?  
{: #account-administrator}
{: faq}

Pour déléguer les fonctions d'administrateur de compte, affectez l'accès suivant :

* Une règle IAM avec le rôle Administrateur pour Tous les services avec l'offre Identity and Access activée, ce qui autorise l'utilisateur à créer des instances de service et à attribuer aux utilisateurs un accès à toutes les ressources du compte.
* Une règle IAM avec le rôle Administrateur pour Tous les services de gestion des comptes, ce qui autorise l'utilisateur à effectuer des tâches comme l'invitation et la suppression d'utilisateurs, la gestion de groupes d'accès, d'ID de service, des offres de catalogue privé et le suivi des informations de facturation et d'utilisation.
* Le droit Super-utilisateur défini pour l'infrastructure classique
* Gestionnaire Cloud Foundry pour toutes les organisations

Même avec l'accès précédemment décrit affecté, un administrateur de compte ne peut pas changer le paramètre d'authentification multi-facteur pour le compte. Seul le propriétaire de compte peut changer ce paramètre.
{: note}

## Quelle est la différence entre un administrateur de compte et un propriétaire de compte ?
{: #owner-administrator}
{: faq}

Le rôle d'administrateur de compte d'{{site.data.keyword.Bluemix_notm}} IAM est automatiquement affecté aux propriétaires de compte. En tant qu'administrateur de compte, vous pouvez inviter des utilisateurs, affecter et gérer l'accès pour les utilisateurs, créer des groupes de ressources, demander l'authentification multi-facteur pour tous les utilisateurs du compte et créer des instances de service. Si vous souhaitez que les autres utilisateurs de votre compte soient également administrateur de compte, affectez-leur l'accès suivant :

* Une règle IAM avec le rôle Administrateur pour Tous les services avec l'offre Identity and Access activée, ce qui autorise l'utilisateur à créer des instances de service et à attribuer aux utilisateurs un accès à toutes les ressources du compte.
* Une règle IAM avec le rôle Administrateur pour Tous les services de gestion des comptes, ce qui autorise l'utilisateur à effectuer des tâches comme l'invitation d'utilisateurs, la gestion de groupes d'accès, d'ID de service, des offres de catalogue privé et le suivi des informations de facturation et d'utilisation.
* Le droit Super-utilisateur défini pour l'infrastructure classique
* Gestionnaire Cloud Foundry pour toutes les organisations

Même avec l'accès précédemment décrit affecté, un administrateur de compte ne peut pas changer le paramètre d'authentification multi-facteur pour le compte. Seul le propriétaire de compte peut changer ce paramètre.
{: note}

## Comment affecter l'accès à l'infrastructure et aux périphériques ?
{: #infrastructure-devices}
{: faq}

1. Accédez à **Gérer** &gt; **Accès (IAM)** puis sélectionnez **Utilisateurs**.
2. Sélectionnez un nom d'utilisateur.
3. Cliquez sur **Infrastructure classique**.
4. Affectez des droits à partir de la section **Droits**, affectez des droits d'accès aux périphériques à partir de la section **Périphériques** puis affectez l'accès aux sous-réseaux VPN pour les périphériques auxquels l'utilisateur a accès, accès affecté à partir de la section **Accès VPN**.

## Tous les utilisateurs de mon compte peuvent-ils voir tous les autres utilisateurs ?
{: #users}
{: faq}

Un propriétaire de compte peut voir tous les utilisateurs du compte et choisir comment les utilisateurs peuvent voir les autres utilisateurs du compte sur la page Utilisateurs. Un propriétaire de compte peut définir le [paramètre de visibilité de liste d'utilisateurs](/docs/iam?topic=iam-userlistview#userlistview) sur la page Paramètres en sélectionnant une des options suivantes :

* **Affichage non restreint** : Tous les utilisateurs du compte peuvent voir tous les membres du compte.
* **Affichage restreint** : Limite la possibilité de voir les utilisateurs sur la page Utilisateurs aux membres disposant d'un accès explicite octroyé ainsi qu'aux membres pouvant voir les autres utilisateurs via une organisation Cloud Foundry partagée ou une relation de hiérarchie d'utilisateurs d'infrastructure classique.


## Dois-je affecter l'accès à un utilisateur lorsque je l'invite à rejoindre le compte ?
{: #account-invite}
{: faq}

Oui. Vous devez affecter un accès utilisateur dans un des trois systèmes de gestion d'accès :

* Une règle d'accès IAM concernant une ressource, un groupe de ressources ou des services de gestion de compte
* Un rôle Cloud Foundry pour une organisation et un espace
* Un droit défini pour l'infrastructure classique


## Comment ajouter l'authentification à mes applications Web et mobiles ?
{: #appid}
{: faq}

IAM permet de gérer l'accès à vos ressources et à vos services {{site.data.keyword.cloud_notm}}. Avec {{site.data.keyword.appid_full_notm}}, vous pouvez améliorer la sécurité du cloud en ajoutant une étape d'authentification à vos applications Web et mobiles. Il suffit d'ajouter quelques lignes de code pour sécuriser facilement vos applications et vos services natifs Cloud qui s'exécutent sur {{site.data.keyword.cloud_notm}}. Prêt à commencer ? [Consultez la documentation](/docs/services/appid?topic=appid-gettingstarted#gettingstarted).
