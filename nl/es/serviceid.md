---

copyright:

  years: 2017, 2019

lastupdated: "2019-05-10"

keywords: service ID, create service ID, lock service ID, service ID example

subcollection: iam

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:tip: .tip}
{:note: .note}

# Creación y trabajo con los ID de servicio
{: #serviceids}

Un ID de servicio identifica un servicio o una aplicación de forma similar a cómo un ID de usuario identifica un usuario. Un ID de servicio que cree puede utilizarse para habilitar una aplicación fuera del acceso de {{site.data.keyword.Bluemix_notm}} a sus servicios de {{site.data.keyword.Bluemix_notm}}. Puede asignar políticas de acceso específicas al ID de servicio que restrinjan permisos para utilizar servicios específicos, o incluso combinar permisos para acceder a servicios distintos. Puesto que los ID de servicio no están vinculados a un usuario específico, si un usuario abandona una organización y se suprime de la cuenta, el ID de servicio seguirá garantizando que su aplicación o servicio permanece activo y en ejecución.
{:shortdesc}

Cuando se crea un ID de servicio, se crea un nombre exclusivo y una descripción que es fácil para identificar y trabajar en la IU. Una vez que haya creado el ID de servicio, puede crear claves de API específicas para cada ID de servicio que la aplicación puede utilizar para autenticarse con los servicios de {{site.data.keyword.Bluemix_notm}}. Para asegurarse de que la aplicación tenga el acceso apropiado para autenticar con los servicios de {{site.data.keyword.Bluemix_notm}}, utilice políticas de acceso asignadas a cada ID de servicio que cree.

Las políticas de acceso asociadas con un ID de servicio permiten acciones específicas que se pueden realizar cuando se utilice dicho ID de servicio para acceder a un servicio específico. Un solo ID de servicio puede tener varias políticas asignadas que definen el nivel de acceso permitido cuando se accede a varios servicios habilitados por Identidad y acceso. Por ejemplo, tiene dos servicios con dos instancias de servicio cada uno. Por ejemplo, puede asignar el rol de visor para todas las instancias disponibles de un servicio y asignar el rol de editor solo para una instancia de un segundo servicio. De esta forma puede personalizar el acceso a varios servicios, pero utilizar una única clave de API para la autenticación en todos ellos.


## Creación de un ID de servicio
{: #create_serviceid}

Para crear un ID de servicio, siga los pasos siguientes:

1. Vaya a **Gestionar** &gt; **Acceso (IAM)** y seleccione **ID de servicio**.
2. Pulse **Crear**.
3. Siga el proceso para crear un nombre y una descripción para el ID de servicio.
4. Pulse **Crear**.

A continuación, pase el puntero del ratón sobre la fila de un ID de servicio para utilizar el menú **Acciones** ![Icono Lista de acciones](../icons/action-menu-icon.svg) para gestionar el ID de servicio. Puede empezar asignando una política y creando claves de API. Para obtener más información sobre cómo trabajar con las claves de API, consulte [Gestión de claves de API de ID de servicio](/docs/iam?topic=iam-serviceidapikeys#serviceidapikeys).

## Actualización de un ID de servicio
{: #update_serviceid}

Puede actualizar un ID de servicio cambiando el nombre y la descripción en cualquier momento. También puede suprimir y crear nuevas claves de API según sea necesario o actualizar las políticas de acceso asignadas. Pase el puntero del ratón sobre la fila de un ID de servicio para utilizar el menú **Acciones** ![Icono Lista de acciones](../icons/action-menu-icon.svg) para gestionar el ID de servicio.

Los cambios que realice en un ID de servicio existente, como por ejemplo cambiar las políticas asignadas o suprimir una clave de API que se está utilizando actualmente, podrían causar interrupciones del servicio para aplicaciones que utilizan dicho ID de servicio.

## Bloqueo de un ID de servicio
{: #lock_serviceid}

Para evitar una situación donde su ID de servicio se suprima provocando una interrupción o alteración para los usuarios del servicio, tiene la opción de bloquear el ID de servicio mediante la IU o CLI. El bloqueo de un ID de servicio también impide que las políticas se cambien, se supriman o se asignen. Además de la capacidad de bloquear un ID de servicio, puede [bloquear claves de API individuales](/docs/iam?topic=iam-lockkey#lockkey) asociadas con cada ID de servicio de la cuenta.

Aunque los ID de servicio bloqueados no se pueden suprimir de la cuenta y las políticas de acceso no se pueden actualizar, los ID de servicio bloqueados se pueden eliminar de cualquier grupo de acceso al que se añadan. Esto significa que cualquier acceso asignado al ID mediante su suscripción en un grupo de acceso se elimina cuando el ID de servicio se elimina del grupo de acceso.
{: note}

### Suministro de acceso de usuario para el bloqueo de los ID de servicio
{: #access_lock_serviceid}

Para que un usuario tenga acceso a bloquear y desbloquear ID de servicio y claves de API asociados con los ID de servicio, deben tener asignados una política de acceso específica. Hay dos tipos de políticas de acceso que pueden otorgar el acceso adecuado: acceso a todos los ID de servicio de la cuenta o acceso a un ID de servicio específico de la cuenta

Para asignar acceso a todos los ID de servicio de la cuenta, establezca una política de acceso para los servicios de gestión de la cuenta con los detalles siguientes:

* Rol de Editor o Administrador
* Servicio de identidad IAM

Para asignar acceso a un ID de servicio específico en la cuenta, establezca una política de acceso para los servicios de gestión de la cuenta con los detalles siguientes:

* Rol de Editor o Administrador
* Servicio de identidad IAM
* Especifique "serviceid" en el campo Tipo de recurso
* Especifique el identificador del ID de servicio en el campo ID de recurso

Para obtener el identificador de un ID de servicio específico, vaya a **Gestionar** > **Acceso (IAM)** y seleccione **ID de servicio**. Seleccione el ID de servicio para el que desea ver detalles, y copie el valor del ID.
{: tip}

### Bloqueo de un ID de servicio desde la IU
{: #lock_serviceid_ui}

Un ID de servicio bloqueado se indica mediante el icono ![icono Bloqueado](images/locked.svg "Bloqueado").

1. En la barra de menús, pulse **Gestionar** &gt; **Acceso (IAM)** y seleccione **ID de servicio**.
2. Identifique la fila del ID de servicio que desea bloquear y seleccione **Bloquear ID de servicio** en el menú **Acciones** ![Icono Lista de acciones](../icons/action-menu-icon.svg).

Para desbloquear un ID de servicio, seleccione el ID de servicio en la tabla que desea desbloquear y seleccione **Desbloquear ID de servicio** en el menú **Acciones** ![Icono Lista de acciones](../icons/action-menu-icon.svg). Debe tener el nivel de acceso apropiado para desbloquear un ID de servicio.
{: tip}


### Bloqueo y desbloqueo de un ID de servicio utilizando la CLI
{: #lock_serviceid_cli}

Para bloquear un ID de servicio, utilice el mandato siguiente:

```
ibmcloud iam service-id-lock (NAME|UUID) [-f, --force]
```

Opciones de mandato:

<dl>
  <dt>NAME (necesario)</dt>
  <dd>Nombre del servicio, exclusivo con UUID</dd>
  <dt>UUID (necesario)</dt>
  <dd>UUID del servicio, exclusivo con NAME</dd>
  <dt>-f, --force</dt>
  <dd>Bloquear sin confirmación</dd>
</dl>

<strong>Ejemplos</strong>:

Bloquear ID de servicio `sample-test` sin confirmación

```
ibmcloud iam service-id-lock sample-test -f
```

Bloquear ID de servicio `ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976`

```
ibmcloud iam service-id-lock ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976
```

Para desbloquear un ID de servicio, utilice el mandato siguiente:

 ```
ibmcloud iam service-id-unlock (NAME|UUID) [-f, --force]
```

Opciones de mandato:

<dl>
  <dt>NAME (necesario)</dt>
  <dd>Nombre del servicio, exclusivo con UUID</dd>
  <dt>UUID (necesario)</dt>
  <dd>UUID del servicio, exclusivo con NAME</dd>
  <dt>-f, --force</dt>
  <dd>Desbloquear sin confirmación</dd>
</dl>

<strong>Ejemplos</strong>:

Desbloquear ID de servicio `sample-test` sin confirmación

```
ibmcloud iam service-id-unlock sample-test -f
```

Desbloquear ID de servicio `ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976`

```
ibmcloud iam service-id-unlock ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976
```


## Ejemplos de cómo utilizar un ID de servicio
{: #examples_serviceid}

A continuación, se muestran ejemplos sobre cómo utilizar un ID de servicio con los servicios {{site.data.keyword.objectstorageshort}} y Cloud SQL Query.

- {{site.data.keyword.objectstorageshort}} - [Uso de la CLI de {{site.data.keyword.Bluemix_notm}}](/docs/services/cloud-object-storage?topic=cloud-object-storage-ic-use-the-ibm-cli#ic-hmac-credentials).
- Cloud SQL Query - [Cómo utilizar la API REST de SQL Query ![Icono de enlace externo](../icons/launch-glyph.svg)](https://www.youtube.com/embed/s6S4AdJItHk?rel=0){: new_window}.
