---

copyright:

  years: 2019

lastupdated: "2019-07-24"

keywords: enterprise access

subcollection: iam

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:tip: .tip}
{:note: .note}

# Gestion des utilisateurs pour les entreprises
{: #enterprise-access}

Les entreprises {{site.data.keyword.cloud}} sont fort utiles pour les organisations ou les sociétés de grande taille ayant besoin de rassembler un ensemble de comptes tout en séparant les comptes des différents services ou des différentes équipes. La gestion des utilisateurs et de leur accès aux ressources dans chaque compte reste entièrement isolée même lorsque les comptes sont ajoutés et organisés dans une entreprise.
{:shortdesc}

Voir [Qu'est-ce qu'une entreprise ?](/docs/account?topic=account-enterprise) pour plus d'informations sur les entreprises.

La liste d'utilisateurs de chaque compte enfant d'une entreprise est accessible uniquement aux utilisateurs de ce compte. Autrement dit, les utilisateurs qui sont invités à rejoindre l'entreprise et ceux qui sont invités à rejoindre les comptes de l'entreprise sont totalement séparés. Cette séparation est particulièrement utile car vous pouvez ajouter plusieurs comptes à une entreprise et les organiser selon vos besoins dans des groupes de comptes tout en empêchant certains utilisateurs d'accéder à d'autres comptes.

Dans la plupart des cas, vous souhaitez ajouter à votre compte d'entreprise uniquement les utilisateurs ayant besoin de pouvoir gérer l'entreprise. En fonction du rôle affecté à l'utilisateur sur le [service de gestion des comptes Entreprise](/docs/iam?topic=iam-assign-access-enterprise), il existe différents niveaux d'accès pour la gestion de l'entreprise. Par exemple, un utilisateur disposant du rôle Administrateur sur le service Entreprise peut renommer l'entreprise, mettre à jour le domaine, consulter l'utilisation, créer des comptes et bien plus encore. Toutefois, un utilisateur disposant du rôle Afficheur ou Opérateur peut uniquement consulter la hiérarchie des comptes et des groupes de comptes pour l'entreprise. 

Le fait d'inviter des utilisateurs à rejoindre le compte de l'entreprise ne leur accorde pas l'accès permettant de gérer les comptes enfant dans l'entreprise ou leurs ressources. Si vous ajoutez un utilisateur à un compte d'entreprise qui contient plusieurs comptes, il ne dispose pas automatiquement de l'accès lui permettant de gérer ces comptes (gestion des utilisateurs, facturation, etc.). Les utilisateurs du compte d'entreprise n'ont pas non plus accès aux ressources des autres comptes de l'entreprise.

Si vous souhaitez qu'un utilisateur puisse gérer l'entreprise et avoir accès aux ressources des comptes enfant, vous devez l'inviter à rejoindre les deux comptes. L'affectation de règles d'accès dans le compte d'entreprise permet à l'utilisateur de gérer l'entreprise. De plus, le fait d'affecter des règles d'accès dans le compte enfant permet à l'utilisateur de gérer des ressources spécifiques ou d'effectuer des tâches de gestion des comptes dans ce compte uniquement.
{: note}

Pour plus d'informations sur l'affectation de l'accès aux utilisateurs d'une entreprise, voir [Affectation de l'accès d'entreprise](/docs/iam?topic=iam-assign-access-enterprise).
