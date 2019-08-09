---

copyright:

  years: 2017, 2019

lastupdated: "2019-07-25"

keywords: user identities, service ID, policies, access management, roles, actions

subcollection: iam

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:external: target="_blank" .external}

# Concepts IAM
{: #iamconcepts}

La rubrique {{site.data.keyword.Bluemix_notm}} Identity and Access Management (IAM) présente deux concepts majeurs. Elle inclut également des informations supplémentaires sur les groupes d'accès, les groupes de ressources, les utilisateurs, les rôles, les règles d'accès, etc.
{: shortdesc}

## Identité
{: #identity}

Le concept d'identité dans {{site.data.keyword.Bluemix_notm}} IAM se compose d'identités d'utilisateur, d'identités de service et d'application, de clés d'API et de ressources. Les utilisateurs sont identifiés par leur IBMid ou leur ID de compte SoftLayer. Les ID de service constituent un deuxième type d'identité utilisé dans un compte. Les ID de service sont la fonctionnalité Cloud IAM utilisée pour fournir une identité distincte aux services et aux applications. Vous pouvez créer un ID de service qu'utilisera une application pour accéder à vos services {{site.data.keyword.Bluemix_notm}} de sorte que les données d'identification d'un utilisateur individuel n'ont pas à être utilisées.

Pour vous authentifier auprès d'une API ou d'une interface CLI en tant qu'ID utilisateur ou de service, il est possible d'utiliser des clés d'API {{site.data.keyword.cloud_notm}}. Etant donné que ces clés d'API sont fournies par le biais de Cloud IAM, elle ne peuvent pas être utilisées de façon générale pour s'authentifier avec un IBMid en dehors d'IBM Cloud. Un utilisateur peut également avoir une clé d'API d'infrastructure classique unique pouvant être utilisée pour accéder aux API d'infrastructure classique. Toutefois, elle n'est pas requise car vous pouvez utiliser des clés d'API {{site.data.keyword.cloud_notm}} pour accéder aux mêmes API.

Les ressources {{site.data.keyword.Bluemix_notm}} constituent l'élément final du concept d'identité dans IAM. Ces ressources sont identifiées par leur nom de ressource de cloud (CRN). Pour plus d'informations, voir [Noms de ressource de cloud](/docs/overview?topic=overview-crn#crn).

## Gestion des accès
{: #am}

Dans {{site.data.keyword.Bluemix_notm}}, le concept de gestion des accès concerne un petit nombre de composants interdépendants, incluant les utilisateurs, les ressources, les règles, les rôles, les actions et le système de contrôle {{site.data.keyword.Bluemix_notm}} IAM, qui autorise des utilisateurs à effectuer des actions sur des ressources au sein d'un compte.

{{site.data.keyword.Bluemix_notm}} IAM suit un modèle [éventuellement cohérent](https://en.wikipedia.org/wiki/Eventual_consistency){: external} commun à un grand nombre de services natifs de cloud, qui permet à IAM de rester hautement disponible et performant dans plusieurs régions globales. Les modifications apportées aux utilisateurs, aux groupes de ressources, aux clés d'API, aux ID de service, aux autorisations, aux règles d'accès IAM ou à tout autre contrôle d'accès sont enregistrées et propagées dans tous les composants IAM et les services activés par IAM dans le monde entier. Les modifications d'accès peuvent ne pas être appliquées avant la fin du processus de propagation.

### Utilisateurs
{: #iam-users}

Tous les utilisateurs d'un compte sont identifiés par leur IBMid ou leur ID de compte SoftLayer. Des utilisateurs peuvent être invités dans le compte et se voir accorder l'accès à des ressources. Les règles d'accès commencent par le sujet qui est souvent un utilisateur de votre compte. L'accès peut être affecté à des services de gestion de compte, à des ressources individuelles, jusqu'au niveau instance, ou à un ensemble de ressources organisées dans un groupe de ressources du compte.


### Groupes d'accès
{: #access-groups-iam}

Un groupe d'utilisateurs et d'ID de service peut être créé de sorte que le même accès puisse être affecté à toutes les entités du groupe avec une ou plusieurs règles. En utilisant des groupes d'accès, vous pouvez rationaliser le processus d'affectation d'accès afin de pouvoir gérer un nombre moins élevé de règles et réduire le nombre de règles dans un compte, ce qui augmente les performances. Une fois que vos groupes sont configurés, vous pouvez commencer à affecter les règles en sélectionnant un groupe d'accès comme sujet de la règle. Pour plus d'informations, voir [Configuration de groupes d'accès](/docs/iam?topic=iam-groups).

### Ressources
{: #resources-access-management}

Les ressources d'un compte sont les offres de service mises à disposition, sélectionnées dans le catalogue, ou des ressources à granularité plus fine au sein d'une instance de service. Ces ressources sont ajoutées à un groupe de ressources lorsqu'elles sont créées à partir du catalogue. La gestion de l'accès IAM permet un accès plus précis, ce qui signifie qu'une règle peut être définie à une plus grande échelle, pour toutes les ressources d'un groupe de ressources, par exemple, ou pour un type de ressource spécifique, comme un compartiment {{site.data.keyword.cos_full_notm}} dans une instance spécifique.


### Règles d'accès
{: #access-policies-concept}

Les règles d'accès déterminent comment des droits spécifiques permettant d'accéder aux ressources de compte sont affectés aux utilisateurs, aux ID de service et aux groupes d'accès du compte. Les règles incluent un sujet, une cible et un rôle. Le sujet correspond à l'utilisateur, à l'ID de service ou au groupe d'accès auquel vous accordez l'accès. La cible de la règle est la ressource à laquelle vous voulez accorder l'accès. Et les rôles permettent de définir le niveau d'accès ou les actions autorisées sur la cible de la règle. Différents types de règle autorisent l'accès aux ressources du compte : règle de groupe de ressources, règle d'instance de ressource, règle au niveau compte pour autoriser l'accès à tous les services activés pour IAM (Identity and Access) ou règle opérant sur tous ou l'un des services de gestion de compte. Selon vos sélections, vous disposez d'options de configuration personnalisées, (par exemple, pour définir l'accès descendant à des ressources d'une région spécifique ou définir l'accès au niveau granulaire d'une ressource spécifique à un service d'une instance).

### Rôles
{: #iam-roles-concept}

Les rôles d'accès Cloud IAM permettent à un utilisateur d'effectuer des tâches spécifiques sur la ressource définie dans la règle. Il existe deux types de rôle d'accès : gestion de plateforme et accès à un service. 

Les rôles de gestion de plateforme définissent les actions autorisées pour la gestion des ressources au niveau de la plateforme, par exemple, l'accès utilisateur et la création d'instances de service. Les rôles de plateforme s'appliquent également aux actions pouvant être effectuées dans le contexte des services de gestion de compte, comme l'invitation et le retrait d'utilisateurs, la gestion de groupes d'accès, d'ID de service et des offres de catalogue privé. 

Les rôles d'accès à un service définissent quant à eux les actions autorisées dans le cadre de l'utilisation d'un service, comme l'appel d'API de service. Ces rôles sont personnalisés en fonction du service sélectionné dans la règle.

### Actions
{: #iam-roles-actions}

Les actions sont mappées aux rôles Cloud IAM afin d'autoriser des utilisateurs à effectuer uniquement les tâches spécifiques associées aux différents rôles qui leur sont affectés. Les actions autorisées pour chaque rôle peuvent varier en fonction du service accédé car chaque service définit comment ce rôle est mappé à l'utilisation du service.

### Système de gestion des accès
{: #access-management-system}

Le système de contrôle de Cloud IAM autorise ou refuse des actions d'utilisateur dans le contexte d'un service sur la base de la règle affectée. Lorsqu'un utilisateur tente d'effectuer une action spécifique, le système de contrôle utilise les attributs définis dans la règle pour déterminer si l'utilisateur est autorisé à effectuer cette tâche.
