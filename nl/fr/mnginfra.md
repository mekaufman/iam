---

copyright:

  years: 2017, 2019

lastupdated: "2019-01-28"

keywords: classic infrastructure access, VPN subnet access, classic infrastructure permissions, device access

subcollection: iam

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:tip: .tip}
{:note: .note}
{:deprecated: .deprecated}

# Gestion de l'accès à l'infrastructure classique
{: #mngclassicinfra}

Vous pouvez mettre à jour les droits pour les services d'infrastructure classique ou ajouter l'accès au périphérique et au sous-réseau VPN pour un utilisateur à tout moment. Pour accéder aux droits d'infrastructure classique, sélectionnez **Gérer** &gt; **Accès (IAM)** puis **Utilisateurs**. Sélectionnez le nom de l'utilisateur pour lequel mettre à jour l'accès puis cliquez sur **Infrastructure classique**.
{:shortdesc}

Le droit de gestion de l'infrastructure classique des utilisateurs ainsi qu'un ancêtre figurant dans la hiérarchie des utilisateurs de l'infrastructure classique doivent vous être affectés. Les propriétaires de compte ont un accès complet au compte, ils ne voient donc pas les droits sur la page. Les utilisateurs individuels ne peuvent pas éditer leurs propres droits, ils ne voient pas non plus les droits sur la page.
{: note}

  1. Sélectionnez **Droits** pour mettre à jour les droits de l'utilisateur. Vous pouvez effectuer une sélection parmi quatre types de droits : compte, périphériques, réseau et services. Sélectionnez individuellement des droits dans chaque catégorie ou utilisez une option d'ensemble de droits pour affecter des droits en bloc.

    Les droits de support et de gestion de compte précédemment affectés aux utilisateurs de votre compte sont désormais migrés des droits d'infrastructure classique vers des groupes d'accès IAM migrés. Pour plus d'informations, voir [Droits d'infrastructure classique migrés](/docs/iam?topic=iam-migrated_permissions).
    {: tip}

  2. Pour octroyer un accès au périphérique utilisateur, sélectionnez **Périphériques** et affectez l'accès aux périphériques et aux types de périphérique, selon les besoins.

    L'accès aux périphériques est affecté une fois que l'utilisateur est invité à rejoindre le compte. Les droits de périphérique s'appliquent aux périphériques spécifiques affectés pour l'utilisateur. Vous pouvez sélectionner des périphériques spécifiques dans la liste ou vous pouvez affecter l'accès par type de périphérique. Si vous choisissez la deuxième option, vous pouvez utiliser les options **Activer un accès ultérieur** pour garantir qu'à chaque ajout de périphérique d'un type spécifique, l'accès à ces périphériques est automatiquement affecté à l'utilisateur.

  3. Pour mettre à jour l'accès d'un utilisateur à des sous-réseaux VPN, sélectionnez **Sous-réseaux VPN**.

    Utilisez l'option **Affectation automatique** pour définir comment l'utilisateur accède aux sous-réseaux VPN en fonction de son accès aux périphériques. Si cette option est activée, l'accès à tous les sous-réseaux des périphériques auxquels l'utilisateur a déjà accès lui est automatiquement affecté. Vous pouvez désactiver cette option pour sélectionner manuellement des sous-réseaux dans la liste.
    {: tip}

    Pour fournir l'accès aux sous-réseaux VPN, l'accès doit déjà être affecté à un ou plusieurs périphériques. Si l'utilisateur n'a accès à aucun périphérique, aucun sous-réseau n'est disponible pour être sélectionné. Vous pouvez définir le type de sous-réseau VPN auquel l'utilisateur a accès en utilisant l'option **Type de réseau privé virtuel**. Si vous sélectionnez **Aucun**, aucun accès au réseau VPN ne peut être affecté.

    L'option PPTP est obsolète. Ainsi, si vous disposez de cette option et que vous la désactivez, elle devient indisponible.
    {: deprecated}
