---

copyright:
  years: 2015, 2019
lastupdated: "2019-04-01"

---

{:tsSymptoms: .tsSymptoms}
{:tsCauses: .tsCauses}
{:tsResolve: .tsResolve}
{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:screen: .screen}
{:codeblock: .codeblock}
{:pre: .pre}
{:note:.deprecated}
{:troubleshoot: data-hd-content-type='troubleshoot'}

# Traitement des incidents liés à IAM
{: #troubleshoot_iam}

Les problèmes généraux en matière d'utilisation d'IAM peuvent être liés à un besoin d'accès à une ressource ou à un compte pour effectuer une tâche, ou à l'identification du type correct d'accès à affecter aux utilisateurs de votre compte pour effectuer des tâches spécifiques. Dans de nombreux cas, ces problèmes peuvent être résolus en quelques opérations simples.
{:shortdesc}

## Comment puis-je savoir quel accès m'est affecté ?
{: #troubleshoot-myaccess}
{: troubleshoot}

Si vous ne disposez pas de l'accès permettant d'effectuer une tâche spécifique (création d'une instance de service et ajout de cette dernière à un groupe de ressource ou invitation à rejoindre le compte s'adressant à d'autres utilisateurs, par exemple), il peut être nécessaire de vérifier l'accès qui vous a été affecté.

Je ne connais pas le niveau d'accès qui m'a été affecté pour effectuer des actions dans un compte dont je suis membre.
{: tsSymptoms}
   
Il est possible que l'accès correct ne vous ait pas été affecté.
{: tsCauses}

Pour vérifier à quelles ressources vous avez accès ainsi que pour connaître le niveau d'accès, procédez comme suit. Si vous avez besoin de demander l'accès, contactez le propriétaire du compte.

Accédez à **Gérer** &gt; **Accès (IAM)** puis sélectionnez votre nom sur la page **Utilisateurs**. Ensuite, selon l'accès que vous recherchez, sélectionnez les différents onglets :
{: tsResolve}

* Pour déterminer l'accès dont vous disposez dans les groupes d'accès auxquels vous êtes affecté, sélectionnez **Groupes d'accès**.
* Pour voir les règles d'accès IAM qui vous sont affectées, sélectionnez l'option **Règles d'accès**.
* Pour voir votre accès Cloud Foundry pour toutes les organisations et tous les espaces, sélectionnez **Accès Cloud Foundry**.


## Comment puis-je disposer de l'accès me permettant d'inviter des utilisateurs à rejoindre le compte ? 
{: #troubleshoot-invite}
{: troubleshoot}

Si vous n'êtes pas le propriétaire du compte et que l'accès correct ne vous est pas affecté, vous ne pouvez pas inviter des utilisateurs à rejoindre un compte. 

Je ne peux pas inviter des utilisateurs à rejoindre le compte.
{: tsSymptoms}
   
Il est possible que l'accès correct ne vous ait pas été affecté.
{: tsCauses}

Pour inviter des utilisateurs et gérer les invitations en attente, vous devez être propriétaire du compte, responsable de l'organisation, être un utilisateur disposant d'une règle d'accès IAM et ayant au moins le rôle Editeur pour le service de gestion des comptes, ou vous devez disposer des droits d'infrastructure classique permettant d'ajouter des utilisateurs.
{: tsResolve}


## Comment puis-je voir les droits d'infrastructure classique des autres utilisateurs ?
{: #troubleshoot-classicinfra}
{: troubleshoot}

Les propriétaires de compte ont un accès complet au compte, ils ne voient donc pas les droits. Les utilisateurs individuels ne peuvent pas éditer leurs propres droits, ils voient les droits sur leur page d'infrastructure classique mais ne peuvent pas les éditer. Vous devez avoir un accès spécifique pour voir et éditer les droits d'un autre utilisateur du compte.

Un message s'affiche indiquant que vous ne pouvez pas consulter les droits d'infrastructure classique d'un autre utilisateur.
{: tsSymptoms}
   
Il est possible que l'accès correct ne vous ait pas été affecté.
{: tsCauses}

Vous devez demander au propriétaire du compte que le droit d'infrastructure classique **Gérer les utilisateurs** vous soit affecté mais vous devez également être un ancêtre de l'utilisateur dans la hiérarchie des utilisateurs de l'infrastructure classique pour voir et gérer les droits d'un autre utilisateur.
{: tsResolve}
