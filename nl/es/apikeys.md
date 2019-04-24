---

copyright:

  years: 2015, 2019
lastupdated: "2019-03-05"

keywords: application programming interface key, API key, API, classic infrastructure API key, IBM Cloud API key

subcollection: iam

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:tip: .tip}

# Visión general de las claves de API
{: #manapikey}

Una clave de interfaz de programación de aplicaciones (clave de API) es un código exclusivo que se pasa a una API para identificar la aplicación o el usuario que efectúa la llamada. Las claves de API se utilizan para realizar un seguimiento y un control sobre la forma la que se utiliza la API, por ejemplo, para impedir un uso malintencionado o abusivo de la misma. La clave de API a menudo actúa a la vez como un identificador exclusivo y como una señal secreta para la autenticación, y habitualmente tiene un conjunto de acceso específico de la identidad asociado a la misma.
{:shortdesc}

Para ver sus claves de API, vaya a **Gestionar** > **Acceso (IAM)** > **Claves de API de IBM Cloud**.

## {{site.data.keyword.cloud_notm}} Claves de API
{: #ibm-cloud-api-keys}

Las claves de API de {{site.data.keyword.cloud}} están asociadas a la identidad del usuario. Solo el usuario con el que está asociada la clave de API puede crearla y suprimirla. Puede utilizar las claves de API de {{site.data.keyword.cloud_notm}} en la interfaz de línea de mandatos (CLI) o como parte de la automatización para iniciar una sesión como su identidad de usuario. También puede utilizar las claves de API de {{site.data.keyword.cloud_notm}} para acceder a las API de infraestructura clásica. Para obtener más información sobre la utilización de una clave de API asociada con su identidad de usuario, consulte [Gestión de las claves de API de usuario](/docs/iam?topic=iam-userapikey#userapikey).

También puede utilizar las claves de API asociadas con los ID de servicio que cree. Los ID de servicio se utilizan para conectar una aplicación dentro o fuera de {{site.data.keyword.Bluemix_notm}} con un servicio de {{site.data.keyword.Bluemix_notm}}. Para obtener más información sobre cómo crear claves de API asociadas con un ID de servicio, consulte [Gestión de claves de API de ID de servicio](/docs/iam?topic=iam-serviceidapikeys#serviceidapikeys).

## Otros tipos de claves de API
{: #othertypes}

Además de sus claves de API de {{site.data.keyword.cloud_notm}}, hay un par de tipos de claves de API disponibles que puede utilizar:

* Claves de API de la infraestructura clásica
* Claves de API específicas del servicio

Las claves de API de la infraestructura clásica se utilizan para llamar a las API para los servicios de la infraestructura clásica. Las claves de API de la infraestructura clásica se deben crear de una en una. Puede crear una clave de API de la infraestructura clásica para un usuario desde la página de detalles de usuario.

También puede utilizar las claves de API de {{site.data.keyword.cloud_notm}} para acceder a las API de la infraestructura clásica.
{: tip}

Es posible que algunos de los servicios de {{site.data.keyword.Bluemix_notm}} ofrezcan una clave de API para que la utilice para trabajar con el servicio. Por ejemplo, si está visualizando los detalles de la oferta de un servicio Watson desde la lista de recursos, puede crear una credencial, que incluya una clave de API y un secreto que son específicos solo para dicho servicio, en la página Credenciales de servicio.
