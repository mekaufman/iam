---

copyright:

  years: 2018, 2019

lastupdated: "2019-05-01"

keywords: IBM Cloud service APIs, IAM token, API key, authenticate with service API

subcollection: iam

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:tip: .tip}

# Invocación de API de servicio de {{site.data.keyword.cloud_notm}}
{: #iamapikeysforservices}

Para invocar un servicio de {{site.data.keyword.Bluemix}} mediante una API, pase sus credenciales a la API del servicio para autenticar su identidad de usuario y su acceso para realizar acciones en el contexto del servicio.
{:shortdesc}

Puede identificar al emisor de la llamada de una de estas formas:

* Clave de API de {{site.data.keyword.Bluemix_notm}} o clave de API de ID de servicio
* Señal de Identity and Access Management (IAM) de {{site.data.keyword.Bluemix_notm}}

Las [claves de API de {{site.data.keyword.Bluemix_notm}}](/docs/iam?topic=iam-userapikey#userapikey), las [claves de API de ID de servicio](/docs/iam?topic=iam-serviceidapikeys#serviceidapikeys) y las señales de IAM identifican de forma exclusiva la identidad del emisor de la llamada.  La identidad del emisor de la llamada es un usuario o un ID de servicio de {{site.data.keyword.Bluemix_notm}} que se ha creado en una cuenta de {{site.data.keyword.Bluemix_notm}}.

Las claves de API son credenciales que constan de una serie larga de caracteres o números aleatorios. Una identidad de {{site.data.keyword.Bluemix_notm}} puede tener varias claves de API. Cada una de estas claves de API se puede gestionar de forma independiente, lo que significa que si solo su servicio utiliza esta clave de API, puede suprimir la clave de la API sin interferir en ningún otro componente.

Puede utilizar claves de API para [iniciar una sesión en la interfaz de línea de mandatos (CLI) de {{site.data.keyword.Bluemix_notm}}](/docs/cli/reference/ibmcloud?topic=cloud-cli-ibmcloud_login#ibmcloud_login) o para [generar señales de IAM](/docs/iam?topic=iam-iamtoken_from_apikey#iamtoken_from_apikey). Aunque no se recomienda para uso de producción, también puede enviar claves de API a los servicios de {{site.data.keyword.Bluemix_notm}}.

## Cómo pasar una clave de API de {{site.data.keyword.Bluemix_notm}} para autenticarse con una API de servicio
{: #apikey_auth}

Los clientes de API pueden pasar directamente una clave de API de {{site.data.keyword.Bluemix_notm}} a la API del servicio de destino. Para ello, envíe la palabra clave `apikey` como nombre de usuario y la clave de API de {{site.data.keyword.Bluemix_notm}} como contraseña utilizando la cabecera HTTP de autorización básica al servicio de destino.

La API del servicio de destino debe realizar la introspección de la clave de API de {{site.data.keyword.Bluemix_notm}} utilizando el servicio {{site.data.keyword.Bluemix_notm}} IAM. En el gráfico siguiente se muestran tres interacciones de API. La clave de API de {{site.data.keyword.Bluemix_notm}} se pasa a cada API del servicio de destino, de modo que cada servicio de destino debe buscar los detalles de la clave de API de {{site.data.keyword.Bluemix_notm}} invocando {{site.data.keyword.Bluemix_notm}} IAM.

![Autenticación con una API de servicio utilizando una clave de API](images/APIkeyauth.svg "Cómo pasar claves de API a servicios de destino que luego pasan la clave de API a IAM para validar credenciales")

El uso de una clave de API de {{site.data.keyword.Bluemix_notm}} resulta cómodo y facilita el descubrimiento de nuevas API y la prueba rápida de prototipos. Este método requiere que envíe la clave de API de {{site.data.keyword.Bluemix_notm}} a la API del servicio de destino en un formato legible, lo que compromete innecesariamente la seguridad de la clave de API. Además, como la API del servicio de destino siempre debe realizar una introspección de la clave de API, este método ofrece un rendimiento menor y, por lo tanto, no se recomienda para cargas de trabajo de producción.

Para autenticarse con una API de servicio utilizando una clave de API, siga los pasos siguientes:

  1. En primer lugar, [cree una clave de API de {{site.data.keyword.Bluemix_notm}}](/docs/iam?topic=iam-userapikey#create_user_key) si aún no lo ha hecho.
  2. Envíe la clave de API de {{site.data.keyword.Bluemix_notm}} tal como se describe en [RFC 7617](https://tools.ietf.org/html/rfc7617){: new_window} ![Icono de enlace externo](../icons/launch-glyph.svg "Icono de enlace externo") como la cabecera HTTP “Authorization”. Utilice `apikey` como nombre de usuario y el valor de la clave de API como contraseña.

Como ejemplo, en los siguientes pasos se utiliza la clave de API 0a1A2b3B4c5C6d7D8e9E:

  1.	Concatene el nombre de usuario `apikey` y la clave de API, separados por un signo de dos puntos: `apikey:0a1A2b3B4c5C6d7D8e9E`
  2.	Codifique la serie en Base64: `base64("apikey:0a1A2b3B4c5C6d7D8e9E") => YXBpa2V5OjBhMUEyYjNCNGM1QzZkN0Q4ZTlF`
  3.	Establezca la cabecera HTTP Authorization con el esquema Basic, por ejemplo `Authorization: Basic YXBpa2V5OjBhMUEyYjNCNGM1QzZkN0Q4ZTlF`. Si utiliza el mandato curl, puede pasar esto con el parámetro -u:

    ```
    curl -u "apikey:<valor de clave de API de IBM Cloud>"
    ```

  Si utiliza otras herramientas, es posible que tenga que especificar estas credenciales de forma distinta.
  {: tip}

## Cómo pasar una señal de {{site.data.keyword.Bluemix_notm}} IAM para autenticarse con una API de servicio
{: #token_auth}

Para recuperar una señal de acceso de IAM, primero el cliente de API debe invocar una API de {{site.data.keyword.Bluemix_notm}} IAM para autenticarse y recuperar dicha señal. La forma recomendada para los clientes de API de servicio de {{site.data.keyword.Bluemix_notm}} es utilizar una clave de API de IAM para obtener una señal de acceso de IAM. La señal de acceso de IAM se puede utilizar para varias invocaciones de servicios de {{site.data.keyword.Bluemix_notm}} que acepten señales de acceso de IAM como método de autenticación. Puesto que las señales de acceso de IAM están firmadas digitalmente con claves asimétricas, los servicios de {{site.data.keyword.Bluemix_notm}} pueden validar una señal de acceso de IAM sin invocar ningún servicio externo. Esto mejora considerablemente el rendimiento de la invocación de una API.

![Autenticación con una API de servicio utilizando una señal de acceso](images/tokenauth.svg "Recuperación de una señal de IAM utilizando una clave de API y pasando la señal de acceso a los servicios de destino para validar credenciales")

Para autenticarse con una API de servicio utilizando una señal de acceso, siga los pasos siguientes:

  1. En primer lugar, [cree una clave de API de {{site.data.keyword.Bluemix_notm}}](/docs/iam?topic=iam-userapikey#create_user_key) si aún no lo ha hecho.
  2. El paso siguiente para el cliente de API es la recuperación de una señal de acceso de IAM, tal como se describe en [Obtención de una señal de IAM a partir de una clave de API](/docs/iam?topic=iam-iamtoken_from_apikey#iamtoken_from_apikey).
  3. A partir de la respuesta, extraiga la propiedad `access_token` para obtener la señal de acceso de IAM. `expires_in` indica los segundos hasta que caduque la señal de acceso de IAM `access_token`. Utilice este valor relativo o la indicación de fecha y hora absoluta `expiration` que depende de la [hora de UNIX](https://en.wikipedia.org/wiki/Unix_time){: new_window} ![Icono de enlace externo](../icons/launch-glyph.svg "Icono de enlace externo").
  4. Envíe la señal de acceso de IAM tal como se describe en [RFC 6750, sección 2.1. Campo de cabecera de solicitud de autorización](https://tools.ietf.org/html/rfc6750#page-5){: new_window} ![Icono de enlace externo](../icons/launch-glyph.svg "Icono de enlace externo"):

Consideremos el ejemplo
siguiente:

  1.	Utilice la cabecera HTTP Authorization
  2.	Antes de la señal de acceso de IAM, utilice como prefijo el literal `Bearer: Bearer eyJhbGciOiJSUzI1Ng...`
  3.	Añada la señal de acceso de IAM con el prefijo a la cabecera HTTP: `Authorization: Bearer eyJhbGciOiJSUzI1Ng...`. Si utiliza el mandato curl, puede pasar esto con el parámetro -H:

    ```
    curl -H "Authorization: Bearer eyJhbGciOiJSUzI1Ng..."
    ```

  Utilice la misma señal de acceso de IAM para las siguientes llamadas de API de servicio de IBM Cloud para mejorar el rendimiento y la escalabilidad.
  {: tip}
