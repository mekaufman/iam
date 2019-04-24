---

copyright:

  years: 2017, 2019

lastupdated: "2019-01-30"

keywords: user state, user status, type of user

subcollection: iam

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:tip: .tip}


# Statut de l'utilisateur
{: #user_status}

Lorsqu'un utilisateur est invité à rejoindre le compte, un statut (en fonction du type d'utilisateur et de l'acceptation de l'invitation) lui est affecté et s'affiche sur sa page **Détails de l'utilisateur**.
{:shortdesc}

| Statut de l'utilisateur | Description |
|:-----------|:------------|
| Actif | L'utilisateur a accepté l'invitation et dispose de l'accès affecté pour pouvoir utiliser le compte. |
| Infrastructure classique désactivée | Le propriétaire du compte ou un utilisateur disposant de droits suffisants peut affecter le statut désactivé à un autre utilisateur afin que ce dernier ne puisse plus accéder aux ressources d'infrastructure classique. L'utilisateur peut continuer à se connecter à la console et à accéder aux ressources de plateforme. |
| VPN uniquement | Utilisateur créé dans le composant mais restreint à l'accès VPN uniquement pour les périphériques. Ce type d'utilisateur ne dispose pas d'un accès lui permettant de se connecter à la console.|
| En cours de traitement | Statut rarement affiché indiquant que l'utilisateur a été ajouté à une invitation mais que cette dernière n'a pas été envoyée et que le système a créé la première instance de l'utilisateur. |
| En attente | Statut indiquant qu'un utilisateur a été invité mais n'a pas accepté l'invitation ou n'a pas rejoint le compte en créant de compte {{site.data.keyword.Bluemix_notm}}. |
{: caption="Tableau 1. Statut de l'utilisateur" caption-side="top"}

Pour plus d'informations sur le changement du statut d'un utilisateur, voir [Mise à jour du statut d'un utilisateur](/docs/iam?topic=iam-status#status).
