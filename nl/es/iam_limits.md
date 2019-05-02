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

# Límites de {{site.data.keyword.Bluemix_notm}} IAM
{: #iam_limits}

La tabla siguiente lista los límites máximos para los recursos de {{site.data.keyword.Bluemix_notm}} Identity and Access Management (IAM). Estos límites se aplican a cualquier usuario que pueda crear recursos de {{site.data.keyword.Bluemix_notm}} IAM; si se supera un límite, recibirá una excepción y no podrá crear ningún recurso nuevo que supere dicho límite.

| Recurso | Máximo |
|----------|---------|
| Grupos de acceso por cuenta | 500 |
| Grupos de acceso por usuario | 50 |
| ID de servicio por cuenta | 2000 |
| Claves de API por identidad | 20 |
| Reglas dinámicas por grupo de acceso | 5 |
{:caption="Tabla 1. Límites de cuenta de IAM" caption-side="top"}

Se recomienda un máximo de 1,000 políticas y servicios en las autorizaciones de servicio de una cuenta para garantizar un rendimiento óptimo en su cuenta.
{: tip}
