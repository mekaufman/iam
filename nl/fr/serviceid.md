---

copyright:

  years: 2017, 2019

lastupdated: "2019-02-21"

keywords: service ID, create service ID, lock service ID, service ID example

subcollection: iam

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:tip: .tip}
{:note: .note}

# Création et utilisation des ID de service
{: #serviceids}

Un ID de service identifie un service ou une application de la même façon qu'un ID utilisateur identifie un utilisateur. Un ID de service que vous créez peut être utilisé pour permettre à une application située en dehors de {{site.data.keyword.Bluemix_notm}} d'accéder à vos services {{site.data.keyword.Bluemix_notm}}. Vous pouvez affecter des règles d'accès spécifiques à l'ID de service qui limitent les droits d'utilisation à des services spécifiques ou bien combiner des droits d'accès à différents services. Les ID de service n'étant pas liés à un utilisateur spécifique, si un utilisateur quitte une organisation et est supprimé du compte, l'ID de service est conservé de sorte que votre application ou service reste fonctionnel.
{:shortdesc}

Lorsque vous créez un ID de service, vous créez un nom unique et une description facilement identifiables et gérables dans l'interface utilisateur. Une fois que vous avez créé votre ID de service, vous pouvez créer des clés d'API propres à chaque ID de service utilisable par votre application pour s'authentifier auprès de vos services {{site.data.keyword.Bluemix_notm}}. Pour faire en sorte que votre application dispose des droits d'accès appropriés pour s'authentifier auprès de vos services {{site.data.keyword.Bluemix_notm}}, utilisez les règles d'accès affectées à chaque ID de service que vous créez.

Les règles d'accès associées à un ID de service permettent d'activer des actions spécifiques qui peuvent être effectuées lorsque cet ID de service est utilisé pour accéder à un service donné. Un ID de service unique peut avoir plusieurs règles affectées qui définissent le niveau d'accès autorisé lors de l'accès à plusieurs services activés par Identity and Access et même à plusieurs instances d'un seul service. Par exemple, vous possédez deux services dotés chacun de deux instances de service. Vous pouvez affecter le rôle Afficheur pour toutes les instances disponibles d'un service et affecter le rôle Editeur pour une seule instance d'un deuxième service. Ainsi, vous pouvez personnaliser l'accès à plusieurs services, mais utiliser une seule clé d'API pour l'authentification auprès de tous les services.


## Création d'un ID de service
{: #create_serviceid}

Pour créer un ID de service, procédez comme suit :

1. Accédez à **Gérer** &gt; **Accès (IAM)** puis sélectionnez **ID de service**.
2. Cliquez sur **Créer**.
3. Suivez le processus afin de créer un nom et une description pour votre ID de service.
4. Cliquez sur **Créer**.

Survolez ensuite la ligne d'un ID de service pour utiliser le menu **Actions** ![Icône Liste des actions](../icons/action-menu-icon.svg) afin de gérer votre ID de service. Vous pouvez commencer par affecter une règle et créer des clés d'API. Pour plus d'informations sur la gestion des clés d'API, voir  [Gestion des clés d'API d'ID de service](/docs/iam?topic=iam-serviceidapikeys#serviceidapikeys).

## Mise à jour d'un ID de service
{: #update_serviceid}

Vous pouvez mettre à jour un ID de service en changeant le nom et la description à tout moment. Vous pouvez également supprimer et créer des clés d'API selon vos besoins ou mettre à jour les règles d'accès affectées. Survolez la ligne d'un ID de service pour utiliser le menu **Actions** ![Icône Liste des actions](../icons/action-menu-icon.svg) afin de gérer votre ID de service.

Chaque fois que vous modifiez un ID de service existant (par exemple, si vous changez les règles affectées ou supprimez une clé d'API en cours d'utilisation), des interruptions de service peuvent se produire sur les applications qui utilisent cet ID de service.

## Verrouillage d'un ID de service
{: #lock_serviceid}

Pour éviter que la suppression de votre ID de service ne provoque une indisponibilité ou une interruption pour les utilisateurs de votre service, vous pouvez verrouiller votre ID de service en utilisant l'interface utilisateur ou l'interface CLI. Le verrouillage d'un ID de service empêche que les règles soient changées, supprimées ou affectées. Non seulement, vous pouvez verrouiller un ID de service mais vous pouvez également [verrouiller des clés d'API individuelles](/docs/iam?topic=iam-lockkey#lockkey) associées à chaque ID de service que vous créez dans votre compte.

Alors que les ID de service ne peuvent pas être supprimés du compte et que les règles d'accès ne peuvent pas être mises à jour, les ID de service verrouillés peuvent toujours être retirés d'un groupe d'accès auquel ils sont ajoutés. Cela signifie que tout accès affecté à l'ID de par son appartenance à un groupe d'accès est retiré dès que l'ID de service ne fait plus partie du groupe d'accès.
{: note}

### Mise à disposition d'un accès utilisateur pour le verrouillage des ID de service
{: #access_lock_serviceid}

Pour qu'un utilisateur puisse verrouiller et déverrouiller des ID de service et des clés d'API associées aux ID de service, une règle d'accès spécifique doit lui être affectée. Deux types de règles d'accès peuvent octroyer l'accès approprié : accès à tous les ID de service du compte ou accès à un ID de service spécifique du compte

Pour accorder un accès à tous les ID de service du compte, définissez une règle d'accès pour les services de gestion de compte d'après les informations suivantes :

* Rôle Editeur ou Administrateur
* Service d'identité IAM

Pour accorder un accès à un ID de service spécifique dans le compte, définissez une règle d'accès pour les services de gestion de compte d'après les informations suivantes :

* Rôle Editeur ou Administrateur
* Service d'identité IAM
* Spécifiez "serviceid" dans la zone Type de ressource
* Indiquez l'identificateur de service dans la zone ID de ressource

Pour obtenir l'identificateur d'un ID de service spécifique, accédez à **Gérer** > **Accès (IAM)** puis sélectionnez **ID de service**. Choisissez l'ID de service pour lequel vous souhaitez afficher les détails puis copiez la valeur de l'ID.
{: tip}

### Verrouillage d'un ID de service à partir de l'interface utilisateur
{: #lock_serviceid_ui}

Un ID de service verrouillé est indiqué par l'icône ![Icône Verrouillé](images/locked.svg "Verrouillé").

1. Dans la barre de menus, cliquez sur **Gérer** &gt; **Accès (IAM)** puis sélectionnez **ID de service**.
2. Identifiez la ligne de l'ID de service que vous souhaitez verrouiller puis sélectionnez **Verrouiller l'ID de service** dans le menu **Actions** ![Icône Liste des actions](../icons/action-menu-icon.svg).

Pour déverrouiller un ID de service, dans le tableau, sélectionnez l'ID de serveur à déverrouiller puis sélectionnez **Déverrouiller l'ID de service** dans le menu **Actions** ![Icône Liste des actions](../icons/action-menu-icon.svg). Vous devez disposer du niveau d'accès approprié pour déverrouiller un ID de service.
{: tip}


### Verrouillage et déverrouillage d'un ID de service à l'aide de l'interface CLI
{: #lock_serviceid_cli}

Pour verrouiller un ID de service, utilisez la commande suivante :

```
ibmcloud iam service-id-lock (NAME|UUID) [-f, --force]
```

Options de commande :

<dl>
  <dt>NAME (obligatoire)</dt>
  <dd>Nom du service, exclut UUID</dd>
  <dt>UUID (obligatoire)</dt>
  <dd>Identificateur unique universel du service, exclut NAME</dd>
  <dt>-f, --force</dt>
  <dd>Verrouiller sans confirmation</dd>
</dl>

<strong>Exemples</strong> :

Verrouiller sans confirmation l'ID de service `sample-test`

```
ibmcloud iam service-id-lock sample-test -f
```

Verrouiller l'ID de service `ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976`

```
ibmcloud iam service-id-lock ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976
```

Pour déverrouiller un ID service, utilisez la commande suivante :

 ```
ibmcloud iam service-id-unlock (NAME|UUID) [-f, --force]
```

Options de commande :

<dl>
  <dt>NAME (obligatoire)</dt>
  <dd>Nom du service, exclut UUID</dd>
  <dt>UUID (obligatoire)</dt>
  <dd>Identificateur unique universel du service, exclut NAME</dd>
  <dt>-f, --force</dt>
  <dd>Déverrouiller sans confirmation</dd>
</dl>

<strong>Exemples</strong> :

Déverrouiller sans confirmation l'ID de service `sample-test`

```
ibmcloud iam service-id-unlock sample-test -f
```

Déverrouiller l'ID de service `ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976`

```
ibmcloud iam service-id-unlock ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976
```


## Exemples d'utilisation d'un ID de service
{: #examples_serviceid}

Vous trouverez ci-après des exemples d'utilisation d'un ID de service avec les services {{site.data.keyword.objectstorageshort}} et Cloud SQL Query.

- {{site.data.keyword.objectstorageshort}} - [Utilisation de l'interface de ligne de commande {{site.data.keyword.Bluemix_notm}}](/docs/services/cloud-object-storage?topic=cloud-object-storage-cli-ic-use-the-ibm-cli#ic-hmac-credentials).
- Cloud SQL Query - [Utilisation de l'API REST SQL Query ![Icône de lien externe](../icons/launch-glyph.svg)](https://www.youtube.com/embed/s6S4AdJItHk?rel=0){: new_window}.
