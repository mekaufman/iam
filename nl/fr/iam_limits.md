---

copyright:
  years: 2018, 2019
lastupdated: "2019-01-30"

---


{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:codeblock: .codeblock}
{:screen: .screen}
{:tip: .tip}

# Limites IAM pour {{site.data.keyword.Bluemix_notm}}
{: #iam_limits}

Le tableau suivant répertorie les limites maximales pour les ressources {{site.data.keyword.Bluemix_notm}} IAM (Identity and Access Management). Ces limites s'appliquent à tous les utilisateurs qui peuvent créer des ressources IAM {{site.data.keyword.Bluemix_notm}}. En cas de dépassement d'une limite, une exception est envoyée à l'utilisateur car celui-ci n'est pas autorisé à créer des ressources au-delà de cette limite.

| Ressource | Max |
|----------|---------|
| Groupes d'accès par compte | 500 |
| Groupes d'accès par utilisateur | 50 | 
| ID de service par compte | 2000 | 
| Clés d'API par identité | 20 |
{:caption="Tableau 1. Limites de compte IAM" caption-side="top"}

Un maximum de 1 000 règles et autorisations de service à service sont recommandées pour un compte afin de garantir des performances optimales au sein de ce compte. 
{: tip}
