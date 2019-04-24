---

copyright:

  years: 2018, 2019

lastupdated: "2019-01-30"

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:tip: .tip}
{:note: .note}

# Création de règles dynamiques pour les groupes d'accès
{: #rules}

Vous pouvez créer des règles dynamiques pour ajouter dynamiquement des utilisateurs fédérés à des groupes d'accès en fonction d'attributs d'identité spécifiques. Lorsque vos utilisateurs se connectent avec un ID fédéré, les données du fournisseur d'identité mappent dynamiquement vos utilisateurs à un groupe d'accès en fonction des règles définies.
{:shortdesc}

Les utilisateurs disposent déjà d'informations d'identité spécifiques liées au domaine de votre entreprise. Lorsqu'ils se connectent avec un ID fédéré, ces données peuvent être transmises en utilisant des assertions SAML. Ces dernières ou les instructions d'attribut configurées dans le fournisseur d'identité mettent à disposition les données utilisées pour la création des règles. Par exemple, il peut exister une instruction d'attribut true ou false qui définit les utilisateurs comme étant responsables. Ces informations peuvent être utilisées pour ajouter les responsables créés dans votre compte {{site.data.keyword.Bluemix_notm}} à un groupe d'accès spécifique. Pour plus d'informations, voir l'[exemple de règle](/docs/iam?topic=iam-rules#example).

Seuls les utilisateurs déjà invités au compte peuvent être mappés aux groupes d'accès en utilisant des règles dynamiques.
{: note}

## Configuration de règles
{: #setup_rules}

Les règles dynamiques sont créées en définissant des conditions devant être respectées par les données configurées dans le fournisseur d'identité et transmises avec un ID fédéré d'utilisateur lors de la connexion. Pour créer une règle, procédez comme suit :

1. Dans la barre de menus, cliquez sur **Gérer** &gt; **Accès (IAM)** puis sélectionnez **Groupes d'accès**.
2. Sélectionnez le nom du groupe d'accès pour lequel vous souhaitez créer une règle afin d'ouvrir la page de détails du groupe.
3. Sélectionnez l'onglet **Règles dynamiques**.
4. Cliquez sur **Ajouter une règle**.
5. Entrez les informations de votre fournisseur d'identité. La liste suivante inclut les détails de chaque zone requise.

<dl>
<dt>Nom</dt>
<dd>Entrez un nom personnalisé pour votre règle afin de vous souvenir plus facilement du type d'utilisateur ajouté à un groupe d'accès.</dd>
<dt>Fournisseur d'identité</dt>
<dd>Entrez l'URI de votre fournisseur d'identité. Il s'agit de la zone "entityId" SAML, parfois appelée ID d'émetteur, pour le fournisseur d'identité comme partie de la configuration de fédération pour l'intégration à IBMid.</dd>
<dt>Expiration (en heures)</dt>
<dd>Vous pouvez utiliser cette option pour améliorer la sécurité en limitant la durée de l'accès affecté. Chaque utilisateur doit se connecter toutes les 24 heures afin d'actualiser leur accès mais vous pouvez définir l'accès de telle sorte qu'il expire au bout d'une heure. L'appartenance au groupe est révoquée une fois cette période écoulée.</dd>
<dt>Ajouter des utilisateurs lorsque</dt>
<dd>Le nom de l'instruction d'attribut doit être entré dans cette zone. Cette valeur est spécifique à votre fournisseur d'identité.</dd>
<dt>Comparateur</dt>
<dd>Vous pouvez choisir Egal à, Non égal à, Est égal à (ignorer la casse), N'est pas égal à (ignorer la casse), Dans ou Contient. Utilisez l'option Contient lorsque l'instruction d'attribut a un type de tableau. Vous pouvez entrer plusieurs valeurs à rechercher en utilisant l'option Dans.</dd>
<dt>Valeur</dt>
<dd>Entrez la valeur d'attribut correspondant à l'instruction utilisée pour la comparaison de la règle.</dd>
</dl>

Vous pouvez ajouter plusieurs conditions pour une règle. Toutes les conditions définies dans la règle doivent être respectées pour qu'un utilisateur soit ajouté à un groupe d'accès.
{: tip}

## Exemple de règle
{: #example}

L'exemple suivant inclut des valeurs pour chaque zone de la page **Ajouter une règle**. Dans cette règle, les utilisateurs identifiés comme responsables dans le fournisseur d'identité fédéré sont mappés à un groupe d'accès {{site.data.keyword.Bluemix_notm}} ayant un accès spécifique défini uniquement pour les responsables.

| Zone | Valeur |
|----------|---------|
| Nom | Règle du groupe de responsables |
| Fournisseur d'identité | `https://idp.example.org/SAML2` |
| Expiration (en heures) | 12 |
| Ajouter des utilisateurs lorsque (nom d'attribut) | isManager |
| Comparateur | Egal à  |
| Valeur |  true |
{: caption="Tableau 1. Exemple de règle dynamique pour les groupes d'accès" caption-side="top"}
