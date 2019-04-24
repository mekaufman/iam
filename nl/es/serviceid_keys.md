---

copyright:

  years: 2015, 2019
lastupdated: "2019-01-30"

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:tip: .tip}
{:note: .note}


# Gestión de claves de API de ID de servicio
{: #serviceidapikeys}

Los ID de servicio se crean para permitir el acceso a los servicios de {{site.data.keyword.Bluemix_notm}} mediante aplicaciones alojadas tanto dentro como fuera de {{site.data.keyword.Bluemix_notm}}. Las claves de API las utiliza una aplicación para autenticarse como un ID de servicio particular y para que se les otorgue el acceso asociado con dicho ID de servicio.

Una vez que haya creado un ID de servicio, puede empezar a crear claves de API y a asignar políticas de servicio. Cada política especifica el nivel de acceso permitido cuando se utiliza la clave de API para autenticarse con los servicios. Para obtener más información sobre la creación de un ID de servicio y la asignación de políticas, consulte [Creación y trabajo con los ID de servicio](/docs/iam?topic=iam-serviceids#serviceids). Para ver detalles sobre los mandatos de CLI que se utilizan para gestionar claves de API de ID de servicio, consulte [Gestión de acceso de IAM, claves de API, ID de servicio y grupos de acceso](/docs/cli/reference/ibmcloud?topic=cloud-cli-ibmcloud_commands_iam#ibmcloud_commands_iam).

Cada clave de API que está asociada con un ID de servicio hereda la política que se ha asignado al ID de servicio. Por ejemplo, si desea que una aplicación pueda simplemente ver recursos dentro de un servicio, necesitará utilizar una clave de API asociada con un ID de servicio que tenga una política asignada con el rol de visor. Y, si desea que otra aplicación pueda tener acceso completo dentro de un servicio, necesitará utilizar una clave de API asociada con un segundo ID de servicio que tenga una política asignada con el rol de administrador.

Para obtener más información, consulte [Ejemplos de cómo utilizar un ID de servicio](/docs/iam?topic=iam-serviceids#examples_serviceid).

## Creación de una clave de API para un ID de servicio
{: #create_service_key}

Crear una clave de API para asociar con un ID de servicio.

1. Vaya a **Gestionar** &gt; **Acceso (IAM)** y seleccione **ID de servicio**.
2. Si no tiene un ID de servicio ya creado, créelo.
3. En el menú **Acciones** ![Icono Lista de acciones](../icons/action-menu-icon.svg), pulse **Gestionar ID de servicio**.
4. Pulse **Claves de API**.
5. Pulse **Crear**.
6. Añada un nombre y una descripción para identificar de forma sencilla la clave de API.
7. Pulse **Crear**.
8. Guarde la clave de API copiándola o descargándola a una ubicación segura.

Por motivos de seguridad, la clave de API sólo está disponible para copiarse o descargarse en el momento de la creación. Si se pierde la clave de API, deberá crear una nueva clave de API.
{: note}

Para crear una clave de API para un ID de servicio utilizando la CLI, puede utilizar el mandato [ibmcloud iam service-api-key-create](/docs/cli/reference/ibmcloud?topic=cloud-cli-ibmcloud_iam_api_key_create#ibmcloud_iam_service_api_key_create).
```
ibmcloud iam service-api-key-create NAME SERVICE_ID [-d, --description DESCRIPTION] [--file FILE] [-f, --force]
```
{: codeblock}

## Actualización de una clave de API para un ID de servicio
{: #update_service_key}

Puede actualizar una clave de API editando el nombre o la descripción utilizada para identificar la clave en la IU.

1. Vaya a **Gestionar** &gt; **Acceso (IAM)** y seleccione **ID de servicio**.
2. En el menú **Acciones** ![Icono Lista de acciones](../icons/action-menu-icon.svg), pulse **Gestionar ID de servicio**.
3. Pulse **Claves de API**.
4. En el menú **Acciones** ![Icono Lista de acciones](../icons/action-menu-icon.svg), pulse **Editar nombre y descripción**.

Para actualizar una clave de API para un ID de servicio utilizando la CLI, puede utilizar el mandato [ibmcloud iam service-api-key-update](/docs/cli/reference/ibmcloud?topic=cloud-cli-ibmcloud_iam_api_key_create#ibmcloud_iam_service_api_key_update).
```
ibmcloud iam service-api-key-update NAME SERVICE_ID  [-n, --name NEW_sNAME] [-d, --description DESCRIPTION] [-v, --version VERSION] [-f, --force]
```
{: codeblock}

## Bloqueo de una clave de API de ID de servicio
{: #lockkey}

Para las claves de API que representan la identidad del ID de servicio, puede impedir que la clave de API se suprima al bloquearla. Una clave de API bloqueada se indica mediante el icono ![icono Bloqueado](images/locked.svg "Bloqueado") en la IU.

1. En la barra de menús, pulse **Gestionar** &gt; **Acceso (IAM)** y seleccione **ID de servicio**.
2. Identifique la fila del ID de servicio para la que desee seleccionar una clave de API y seleccione el nombre del ID de servicio.
3. Pulse **Claves de API**.
4. Pase el ratón sobre la fila de la clave de API que desea bloquear y pulse el menú **Acciones** ![Icono Lista de acciones](../icons/action-menu-icon.svg) para abrir una lista de acciones.
5. Pulse **Bloquear clave de API**.

Puede desbloquear su clave de API en cualquier momento para actualizar, suprimir o añadir una política de acceso, o para eliminar la clave de API.
{: tip}

### Bloqueo o desbloqueo de una clave de API de ID de servicio con la CLI
{: #lock_unlock_cli}

Para bloquear una clave de API de ID de servicio, utilice el mandato siguiente:

```
ibmcloud iam service-api-key-lock (APIKEY_NAME|APIKEY_UUID) (SERVICE_ID_NAME|SERVICE_ID_UUID) [-f, --force]
```

<strong>Requisitos previos</strong>: Punto final, inicio de sesión, destino

<strong>Opciones de mandato</strong>:
<dl>
  <dt>APIKEY_NAME (necesario)</dt>
  <dd>Nombre de la clave de API, exclusivo con APIKEY_UUID</dd>
  <dt>APIKEY_UUID (necesario)</dt>
  <dd>UUID de la clave de API, exclusivo con APIKEY_NAME</dd>
  <dt>SERVICE_ID_NAME (necesario)</dt>
  <dd>Nombre del ID de servicio, exclusivo con SERVICE_ID_UUID</dd>
  <dt>SERVICE_ID_UUID (necesario)</dt>
  <dd>UUID del ID de servicio, exclusivo con SERVICE_ID_NAME</dd>
  <dt>-f, --force</dt>
  <dd>Bloquear sin confirmación</dd>
</dl>

<strong>Ejemplos</strong>:

Bloquear clave de API de servicio `sample-key` del ID de servicio `sample-service`:

```
ibmcloud iam service-api-key-lock sample-key sample-service
```

Para desbloquear una clave de API de ID de servicio, utilice el mandato siguiente:

```
ibmcloud iam service-api-key-unlock (APIKEY_NAME|APIKEY_UUID) (SERVICE_ID_NAME|SERVICE_ID_UUID) [-f, --force]
```


## Supresión de una clave de API para un ID de servicio
{: #delete_service_key}

Puede suprimir una clave de API que esté asociada con un ID de servicio. Sin embargo, suprimir una clave de API que está utilizando actualmente una aplicación eliminará la capacidad de dicha aplicación para autenticarse con los servicios.

1. Vaya a **Gestionar** &gt; **Acceso (IAM)** y seleccione **ID de servicio**.
2. Si no tiene un ID de servicio ya creado, créelo.
3. En el menú **Acciones** ![Icono Lista de acciones](../icons/action-menu-icon.svg), pulse **Gestionar ID de servicio**.
4. Pulse **Claves de API**.
5. En el menú **Acciones** ![Icono Lista de acciones](../icons/action-menu-icon.svg), pulse **Suprimir**.

Para suprimir una clave de API para un ID de servicio utilizando la CLI, puede utilizar el mandato [ibmcloud iam service-api-key-delete](/docs/cli/reference/ibmcloud?topic=cloud-cli-ibmcloud_iam_api_key_create#ibmcloud_iam_service_api_key_delete).
```
ibmcloud iam service-api-key-delete NAME SERVICE_ID [-f, --force]
```
{: codeblock}
