---

copyright:

  years: 2015, 2019
lastupdated: "2019-01-30"

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}

# Gestion des clés d'API d'utilisateur
{: #userapikey}

Un utilisateur, fédéré ou non, peut créer une clé d'API afin de l'utiliser depuis l'interface CLI ou, dans le cadre de l'automatisation, pour se connecter sous votre identité d'utilisateur. Vous pouvez utiliser l'interface utilisateur ou l'interface de ligne de commande pour gérer vos clés d'API en les répertoriant, en créant des clés, en les mettant à jour, ou en les supprimant. Pour gérer les clés d'API {{site.data.keyword.Bluemix_notm}} associées à votre identité utilisateur, accédez à **Gérer** &gt; **Accès (IAM)** puis sélectionnez **Utilisateurs**. Cliquez sur votre nom dans la liste puis sélectionnez l'option **Détails de l'utilisateur** pour obtenir la liste de vos clés d'API incluant les descriptions et les dates. Vous pouvez alors créer, modifier ou supprimer des clés d'API. Pour obtenir la liste complète des commandes CLI disponibles, voir [`ibmcloud iam api-keys`](/docs/cli/reference/ibmcloud?topic=cloud-cli-ibmcloud_commands_iam#ibmcloud_iam_api_keys).

En tant qu'[utilisateur fédéré](/docs/account?topic=account-signup#signup), vous pouvez utiliser une clé d'API pour vous connecter en utilisant la variable d'environnement `IBMCLOUD_API_KEY`. Pour plus d'informations sur l'utilisation d'une clé d'API pour la connexion, voir [Connexion à l'aide d'un ID fédéré](/docs/iam?topic=iam-federated_id#federated_id).
{:shortdesc}

## Création d'une clé d'API
{: #create_user_key}

En tant qu'utilisateur {{site.data.keyword.Bluemix_notm}}, vous pouvez choisir d'utiliser une clé d'API lorsque vous activez un programme ou un script sans distribuer votre mot de passe au script. L'utilisation d'une clé d'API présente l'avantage suivant : un utilisateur ou une organisation peut créer plusieurs clés d'API pour divers programmes et les clés d'API peuvent être supprimées indépendamment si elles sont compromises sans interférence avec d'autres clés d'API, ou l'utilisateur. Vous pouvez créer jusqu'à 20 clés d'API.

Pour créer une clé d'API pour votre identité d'utilisateur dans l'interface utilisateur, procédez comme suit :

1. Accédez à **Gérer** &gt; **Accès (IAM)** puis sélectionnez **Utilisateurs**. Cliquez sur votre nom dans la liste et sélectionnez l'option **Détails de l'utilisateur**.
2. Cliquez sur **Créer une clé d'API{{site.data.keyword.Bluemix_notm}}**.
3. Entrez un nom et une description pour votre clé d'API.
4. Cliquez sur **Créer**.
5. Ensuite, cliquez sur **Afficher** afin d'afficher la clé d'API pour la copier et la sauvegarder en vue d'une utilisation ultérieure, ou cliquez sur **Télécharger**.

Pour des raisons de sécurité, la clé d'API ne peut être copiée ou téléchargée qu'au moment de sa création. Si la clé d'API est perdue, vous devez en créer une autre.
{: tip}

Pour créer une clé d'API dans l'interface de ligne de commande (CLI), utilisez la commande suivante :

1. Entrez `ibmcloud iam api-key-create NAME [-d DESCRIPTION] [-f, --file FILE]` dans votre invite de commande et spécifiez un nom, une description et un fichier pour l'enregistrement de votre clé. Voir l'exemple suivant :

```
ibmcloud iam api-key-create MyKey -d "this is my API key" --file key_file
``` 


## Mise à jour d'une clé d'API
{: #update_user_key}

Si vous désirez modifier le nom ou la description d'une clé d'API, procédez comme suit dans l'interface de ligne de commande ou l'interface utilisateur.

Pour modifier une clé d'API, procédez comme suit :

1. Accédez à **Gérer** &gt; **Accès (IAM)** puis sélectionnez **Utilisateurs**. Cliquez sur votre nom dans la liste et sélectionnez l'option **Détails de l'utilisateur**.
2. Identifiez la ligne correspondant à la clé d'API à mettre à jour puis sélectionnez **Editer** dans le menu **Actions** ![Icône Liste des actions](../icons/action-menu-icon.svg).
3. Mettez à jour les informations relatives à votre clé d'API.
4. Cliquez sur **Appliquer**.

Pour modifier une clé d'API en utilisant l'interface CLI, entrez la commande suivante :

1. Entrez `ibmcloud iam api-key-update NOM [-n NAME] [-d DESCRIPTION]` dans votre invite de commande, en spécifiant l'ancien nom, le nouveau et la nouvelle description de la clé. Par exemple :

```
ibmcloud iam api-key-update MyCurrentName -n MyNewName -d "the new description of my key"
```

## Verrouillage d'une clé d'API
{: #lock_user_key}

Vous pouvez empêcher la suppression des clés d'API de plateforme représentant votre identité utilisateur en les verrouillant. Une clé d'API verrouillée est indiquée par l'icône ![Icône Verrouillé](images/locked.svg "Verrouillé"). Vous pouvez verrouiller et déverrouiller votre clé d'API en utilisant l'interface utilisateur ou l'interface CLI.

### Verrouillage et déverrouillage d'une clé d'API à partir de l'interface utilisateur
{: #lockui}

1. Accédez à **Gérer** &gt; **Accès (IAM)** puis sélectionnez **Utilisateurs**. Cliquez sur votre nom dans la liste et sélectionnez l'option **Détails de l'utilisateur**.
2. Identifiez la ligne correspondant à la clé d'API à verrouiller puis sélectionnez **Verrouiller** dans le menu **Actions** ![Icône Liste des actions](../icons/action-menu-icon.svg).

Vous pouvez déverrouiller votre clé d'API à tout moment pour mettre à jour ou retirer la clé d'API dans votre compte. Dans le tableau, sélectionnez la clé d'API à déverrouiller puis sélectionnez **Déverrouiller** dans le menu **Actions** ![Liste des actions](../icons/action-menu-icon.svg).
{: tip}

### Verrouillage et déverrouillage d'une clé d'API à l'aide de l'interface CLI
{: #lockcli}

Pour verrouiller une clé d'API, utilisez la commande suivante :

```
ibmcloud iam api-key-lock (NAME|UUID) [-f, --force]
```

<strong>Prérequis</strong> : Noeud final, Connexion

<strong>Options de commande</strong> :
<dl>
<dt>NAME (obligatoire)</dt>
<dd>Nom de la clé d'API à verrouiller, exclut UUID.</dd>
<dt>UUID (obligatoire)</dt>
<dd>Identificateur unique universel de la clé d'API à verrouiller, exclut NAME.</dd>
<dt>-f, --force</dt>
<dd>Forcer le verrouillage sans confirmation.</dd>
</dl>

<strong>Exemple</strong> :

Verrouiller la clé d'API `test-api-key`

```
ibmcloud iam api-key-lock test-api-key
```

Pour déverrouiller une clé d'API, exécutez la commande suivante :

```
ibmcloud iam api-key-unlock (NAME|UUID) [-f, --force]
```

<strong>Prérequis</strong> : Noeud final, Connexion

<strong>Options de commande</strong> :
<dl>
<dt>NAME (obligatoire)</dt>
<dd>Nom de la clé d'API à déverrouiller, exclut UUID.</dd>
<dt>UUID (obligatoire)</dt>
<dd>Identificateur unique universel de la clé d'API à déverrouiller, exclut NAME.</dd>
<dt>-f, --force</dt>
<dd>Forcer le déverrouillage sans confirmation.</dd>
</dl>

<strong>Exemple</strong> :

Déverrouiller la clé d'API `test-api-key`

```
ibmcloud iam api-key-unlock test-api-key
```


## Suppression d'une clé d'API
{: #delete_user_key}

Si vous utilisez une stratégie de rotation des clés, vous pouvez être amené à supprimer une ancienne clé et la remplacer par une nouvelle.

Pour supprimer une clé d'API, procédez comme suit : 

1. Accédez à **Gérer** &gt; **Accès (IAM)** puis sélectionnez **Utilisateurs**. Cliquez sur votre nom dans la liste et sélectionnez l'option **Détails de l'utilisateur**.
2. Identifiez la ligne correspondant à la clé d'API à supprimer puis sélectionnez **Supprimer** dans le menu **Actions** ![Icône Liste des actions](../icons/action-menu-icon.svg).
3. Confirmez ensuite la suppression en cliquant sur **Supprimer**.

Pour supprimer une clé d'API à l'aide de l'interface de ligne de commande :
1. Entrez `ibmcloud iam api-key-delete NAME` dans votre invite de commande, en indiquant le nom de la clé à supprimer.
