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

# Limites do {{site.data.keyword.Bluemix_notm}} IAM
{: #iam_limits}

A tabela a seguir lista os limites máximos para recursos do {{site.data.keyword.Bluemix_notm}} Identity and Access Management (IAM). Esses limites se aplicam a qualquer usuário que possa criar recursos do {{site.data.keyword.Bluemix_notm}} IAM e, se um limite for excedido, você receberá uma exceção e não poderá criar nenhum novo recurso além desse limite.

| Recurso | Máx. |
|----------|---------|
| Grupos de acesso por conta | 500 |
| Grupos de acesso por usuário | 50 |
| IDs de serviço por conta | 2000 |
| Chaves API por identidade | 20 |
| Regras dinâmicas por grupo de acesso | 5 |
{:caption="Tabela 1. Limites de conta do IAM" caption-side="top"}

Um máximo de 1.000 políticas e autorizações de serviço para serviço dentro de uma conta é recomendado para assegurar o desempenho ideal em sua conta.
{: tip}
