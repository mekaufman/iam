---

copyright:

  years: 2018, 2019

lastupdated: "2019-05-16"

keywords: event tracking, IAM events, monitoring

subcollection: iam

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:tip: .tip}
{:note: .note}
{:deprecated: .deprecated}

# Seguimiento de sucesos IAM
{: #tracking}

Como responsable de seguridad, auditor o gestor, puede utilizar el servicio de {{site.data.keyword.at_full}} para realizar el seguimiento de cómo interactúan los usuarios y las aplicaciones con {{site.data.keyword.Bluemix_notm}} Identity and Access Management (IAM).
{:shortdesc}

A partir del 9 de mayo de 2019, el servicio {{site.data.keyword.cloudaccesstraillong}} queda obsoleto. Deberá crear una instancia de {{site.data.keyword.at_short}} en su cuenta para continuar con el seguimiento de los sucesos de IAM. Para obtener más información, consulte [Desuso del servicio IBM Cloud Activity Tracker](https://www.ibm.com/blogs/bluemix/2019/04/deprecating-ibm-cloud-activity-tracker/){: new_window} ![Icono de enlace externo](../icons/launch-glyph.svg "Icono de enlace externo").
{: deprecated}

Puede realizar un seguimiento de los siguientes sucesos:

* Gestión de grupos de acceso mediante la creación y supresión de grupos o la adición y eliminación de usuarios
* Creación, actualización o supresión de ID de servicio
* Creación, actualización o supresión de claves de API
* Creación, actualización o supresión de políticas de acceso
* Inicio de sesión en {{site.data.keyword.Bluemix_notm}} utilizando una clave de API, un código de autorización, un código de acceso, una contraseña o una clave de API asociada con un ID de servicio

Para empezar a supervisar las acciones del usuario, consulte [{{site.data.keyword.at_short}}](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-getting-started#getting-started). Para obtener más información sobre cada una de las áreas de sucesos de las que puede realizar un seguimiento, consulte [Sucesos de IAM](/docs/services/Activity-Tracker-with-LogDNA?topic=logdnaat-at_events_iam).
