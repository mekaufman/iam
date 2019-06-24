---

copyright:
  years: 2018, 2019
lastupdated: "2019-03-08"

keywords: maximum limits, IBM Cloud IAM, limits, maximum policies

subcollection: iam

---


{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:codeblock: .codeblock}
{:screen: .screen}
{:tip: .tip}

# Limites IAM pour {{site.data.keyword.Bluemix_notm}}
{: #iam_limits}

Le tableau suivant répertorie les limites maximales pour les ressources {{site.data.keyword.Bluemix_notm}} IAM (Identity and Access Management). Ces limites s'appliquent à tout utilisateur capable de créer des ressources IAM {{site.data.keyword.Bluemix_notm}}. Si une limite est dépassée, vous recevez une exception et n'êtes plus autorisé à créer de nouvelles ressources au-delà de cette limite.
{:shortdesc}

| Ressource | Max |
|----------|---------|
| Groupes d'accès par compte | 500 |
| Groupes d'accès par utilisateur | 50 |
| ID de service par compte | 2000 |
| Clés d'API par identité | 20 |
| Règles dynamiques par groupe d'accès | 5 |
{:caption="Tableau 1. Limites de compte IAM" caption-side="top"}

Un maximum de 1 000 règles et autorisations de service à service sont recommandées pour un compte afin de garantir des performances optimales au sein de ce compte.
{: tip}
