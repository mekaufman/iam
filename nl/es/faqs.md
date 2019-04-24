---



copyright:

  years: 2018, 2019

lastupdated: "2019-03-19"

keywords: frequently asked question, faq

subcollection: iam

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:tip: .tip}
{:faq: data-hd-content-type='faq'}
{:note: .note}

# Preguntas más frecuentes
{: #iamfaq}

## ¿Qué es {{site.data.keyword.cloud_notm}} Identity and Access Management?
{: #whatisiam}
{: faq}

Identity and Access Management (IAM) le permite autenticar usuarios de forma segura para servicios de la plataforma y controlar el acceso a los recursos de la plataforma {{site.data.keyword.cloud_notm}}. Se ha habilitado un conjunto de servicios de IBM Cloud para que utilicen Cloud IAM para el control de accesos. Están organizados en grupos de recursos dentro de su cuenta para que pueda otorgar a los usuarios acceso rápido y sencillo a más de un recurso a la vez. Las políticas de acceso de Cloud IAM se utilizan para asignar accesos de usuario e ID de servicio a los recursos de su cuenta. Para obtener más información, consulte [{{site.data.keyword.cloud_notm}} Identity and Access Management](/docs/iam?topic=iam-iamoverview#iamoverview).

## ¿Qué es un servicio habilitado para IAM?
{: #iam-enabled}
{: faq}

Un servicio habilitado para IAM debe estar en un grupo de recursos y el acceso al servicio se proporciona mediante las políticas de acceso de IAM. Cuando cree un servicio habilitado para IAM desde el catálogo, debe asignarlo a un grupo de recursos. Para obtener más información, consulte [¿Qué es un recurso?](/docs/resources?topic=resources-resource#resource)

{{site.data.keyword.containerlong_notm}} es la única excepción; el acceso se controla mediante IAM, pero siempre se asigna al grupo de recursos predeterminado. Por lo tanto, no tiene la opción de elegir uno cuando lo crea desde el catálogo. Y no se puede asignar a ningún otro grupo de recursos


## ¿Están relacionados IAM y Cloud Foundry?
{: #iam-cloudfoundry}
{: faq}

No están relacionados. Cloud Foundry es una plataforma de código abierto que utiliza organizaciones, espacios y roles de Cloud Foundry para la gestión de accesos. IAM constituye el método seguro de autenticar usuarios para servicios de la plataforma y para controlar el acceso a los recursos en la plataforma {{site.data.keyword.cloud_notm}} utilizando grupos de recursos y roles de acceso de IAM.

Los sistemas de gestión de accesos son totalmente diferentes. Los recursos de IAM pertenecen a un grupo de recursos y los recursos de Cloud Foundry pertenecen a una organización y un espacio. Las políticas de acceso de IAM se utilizan para proporcionar acceso a los recursos de un grupo de recursos. Y los roles de organización y de espacio de Cloud Foundry se utilizan para proporcionar a los usuarios acceso a los recursos de Cloud Foundry en un espacio. IAM no le da acceso a nada dentro de los espacios de Cloud Foundry, y los roles de Cloud Foundry no pueden otorgar acceso a recursos dentro de un grupo de recursos.

## ¿Cómo puedo averiguar a qué tengo acceso?
{: #iam-access}
{: faq}

Vaya a **Gestionar** &gt; **Acceso (IAM)** y seleccione su nombre en la página Usuarios. Luego, en función del acceso que busque, abra los distintos separadores:

* Para determinar qué acceso tiene en los grupos de acceso que tiene asignados, seleccione **Grupos de acceso**.
* Para ver las políticas de acceso de IAM que tiene asignadas, seleccione **Políticas de acceso**.
* Para ver el acceso de Cloud Foundry para todas las organizaciones y espacios, seleccione **Acceso de Cloud Foundry**.


## ¿Cómo puedo solicitar acceso a un recurso?
{: #request-access}
{: faq}

El propietario de la cuenta puede actualizar su acceso a cualquier recurso de la cuenta, o bien puede ponerse en contacto con cualquier usuario que tenga asignado el rol de administrador sobre el servicio o la instancia de servicio.

## ¿Por qué debo utilizar grupos de recursos y grupos de acceso?
{: #resource-groups}
{: faq}

Un grupo de recursos es un contenedor lógico para los recursos. Cuando se crea un recurso, se asigna a un grupo de recursos y no se puede mover después de que se añada.

Un grupo de acceso se utiliza para organizar fácilmente un conjunto de usuarios e ID de servicio en una sola entidad para facilitar las asignaciones de acceso. Puede asignar una única política a un grupo de acceso para otorgar dichos permisos a todos los miembros. Si tiene más de un usuario o ID de servicio que necesita el mismo acceso, cree un grupo de acceso en lugar de asignar el mismo acceso varias veces por usuario o ID de servicio individual.

Mediante el uso de grupos de recursos y de grupos de acceso, puede agilizar la política de asignación de acceso al asignar un número limitado de políticas. Puede organizar todos los recursos a los que debe acceder un grupo específico de usuarios y de ID de servicio en un solo grupo de recursos, agrupar todos los usuarios o ID de servicio en un grupo de acceso y luego asignar una única política que dé acceso a todos los recursos en el grupo de recursos.

Para obtener más información, consulte [Prácticas recomendadas para asignar acceso](/docs/iam?topic=iam-account_setup#account_setup).

## ¿Cómo puedo asegurarme de que mis usuarios pueden crear recursos dentro de un grupo de recursos?
{: #resources}
{: faq}

Para crear un recurso en un grupo de recursos, el usuario debe tener dos políticas de acceso: una asignada al propio grupo de recursos y una asignada a los recursos del grupo. El acceso al propio grupo de recursos es simplemente el acceso al contenedor que organiza los recursos, y este tipo de política permite a un usuario ver, editar o gestionar el acceso al grupo, pero no los recursos contenidos en el mismo. El acceso a los servicios contenidos en el grupo de recursos permite a un usuario trabajar con las instancias de servicio, lo que significa que el usuario puede crear una instancia de servicio.

Por lo tanto, como mínimo el usuario debe tener el siguiente acceso:

* Rol de visor o superior sobre el propio grupo de recursos
* Rol de editor o superior sobre el servicio o sobre todos los servicios del grupo de recursos


## ¿Qué acceso necesito para proporcionar acceso a otros usuarios?
{: #user-access}
{: faq}

Para los servicios habilitados para IAM, debe tener el rol de administrador sobre el servicio o recurso al que desea asignar acceso a los usuarios. Si desea asignar acceso a todos los servicios o recursos de la cuenta, necesita una política sobre todos los servicios habilitados para Identity and Access con el rol de administrador. Además, para asignar a los usuarios acceso a los servicios de gestión de la cuenta, debe tener asignado el rol de administrador sobre el servicio específico o sobre todos los servicios de gestión de la cuenta.

Para los servicios de Cloud Foundry, debe tener los roles de gestor de organización y de espacio de Cloud Foundry para otorgar acceso a los recursos de Cloud Foundry.

Para la infraestructura clásica, debe tener el permiso de la infraestructura clásica Gestionar usuario y los permisos de categoría de servicio y de dispositivos para los recursos a los que desea otorgar acceso al usuario.

## ¿Qué diferencia hay entre proporcionar acceso para gestionar un grupo de recursos y proporcionar acceso a los recursos contenidos en un grupo de recursos?
{: #providing-access}
{: faq}

Si tiene acceso para gestionar un grupo de recursos, puede ver, editar el nombre y gestionar el acceso para el propio grupo de recursos, en función del rol asignado. El acceso a un grupo de recursos en sí no da al usuario acceso a los recursos contenidos en el grupo.

Si tiene acceso a los recursos contenidos en un grupo de recursos, puede editar, suprimir y crear instancias, o bien puede tener acceso a todas las acciones de gestión para los servicios especificados dentro del grupo de recursos, en función del rol asignado.

Para ver acciones y roles de gestión de plataforma de ejemplo para servicios de gestión de cuentas, consulte la [Tabla de roles de plataforma](/docs/iam?topic=iam-userroles#platformrolestable2).

## ¿Quién puede eliminar usuarios?
{: #remove-users}
{: faq}

El propietario de la cuenta puede eliminar cualquier usuario de la cuenta, y cualquier usuario con el siguiente acceso puede eliminar usuarios de una cuenta:

* Una política de IAM para el servicio de gestión de cuenta de gestión de usuarios con el rol de administrador asignado y debe ser el gestor de organización de Cloud Foundry si el usuario pertenece a una organización de Cloud Foundry.
* Si tiene la infraestructura clásica en su cuenta, un usuario debe tener una política de IAM para el servicio de gestión de cuenta de gestión de usuarios con el rol de administrador asignado, debe ser el gestor de organización de Cloud Foundry si el usuario pertenece a una organización de Cloud Foundry y debe ser un antecesor del usuario en la jerarquía de usuarios de la infraestructura clásica con el permiso de gestión de usuarios de infraestructura clásica asignado.

## ¿Cómo puedo imponer la autenticación de multifactores de IBMid para mi cuenta?
{: #multi-factor}
{: faq}

1. Vaya a **Gestionar** &gt; **Acceso (IAM)** y seleccione **Valores**.
2. En la sección Inicio de sesión de cuenta, seleccione **Actualizar** para seleccionar MFA para todos los usuarios o solo para los usuarios no federados.

Para obtener más información, consulte [Requerimiento de MFA para los usuarios de la cuenta](/docs/iam?topic=iam-enablemfa#enablemfa).

## ¿Qué diferencia hay entre los roles de servicio y de plataforma?
{: #service-platform-roles}
{: faq}

Los roles de servicio y de plataforma son dos tipos distintos de roles:

* Los roles de plataforma están relacionados con la forma en que trabaja con un servicio dentro de una cuenta, como por ejemplo crear instancias, enlazar instancias y gestionar el acceso de usuario al servicio. Para los servicios de plataforma, estos roles permiten a los usuarios crear grupos de recursos y gestionar los ID de servicio, por ejemplo. Los roles de plataforma son: administrador, editor, operador y visor.

* Los roles de servicio definen la capacidad de realizar acciones sobre un servicio y son específicos de cada servicio, como por ejemplo realizar llamadas de API o acceder a la interfaz de usuario. Los roles de servicio son: gestor, escritor y lector. Para obtener más información sobre cómo se aplican estos roles, consulte la documentación del servicio específico.

## ¿Qué diferencia hay entre un grupo de recursos y las organizaciones y los espacios de Cloud Foundry?
{: #groups-organizations}
{: faq}

Al comienzo de {{site.data.keyword.Bluemix_notm}}, un servicio de plataforma de código abierto para el control de accesos y la organización de recursos denominado Cloud Foundry era el único método para organizar y controlar el acceso a los recursos. A medida que {{site.data.keyword.Bluemix_notm}} se fue ampliando, surgió la necesidad de disponer de un nuevo método que pudieran utilizar todos los tipos de servicios y recursos. Ahora se utilizan grupos de recursos para agrupar y organizar muchos tipos de recursos, y se utiliza IAM para controlar de forma coherente el acceso a los servicios y recursos. Varios servicios ya han adoptado el uso de grupos de recursos y de IAM, y otros servicios pasarán con el tiempo a utilizar el nuevo método para organizar recursos y gestionar el acceso.

El control de accesos y la organización de los recursos de la cuenta son las principales diferencias entre los grupos de recursos y las organizaciones y espacios de Cloud Foundry. Los grupos de recursos organizan los servicios habilitados para IAM en una cuenta cuyo acceso se controla mediante políticas de IAM. Las organizaciones y los espacios se gestionan utilizando roles de Cloud Foundry para el control de accesos y se asignan recursos de Cloud Foundry a espacios. Las organizaciones y los espacios se pueden utilizar para organizar y controlar el acceso a los recursos solo dentro del dominio de Cloud Foundry, mientras que los grupos de recursos e IAM se pueden utilizar para varios tipos de recursos en {{site.data.keyword.Bluemix_notm}}.

## ¿Cómo se delegan las funciones de administrador de la cuenta?  
{: #account-administrator}
{: faq}

Para delegar las funciones de administrador de la cuenta, asigne el siguiente acceso:

* Una política de IAM con el rol de administrador sobre todos los servicios habilitados para Identity and Access, lo que permite a un usuario crear instancias de servicio y asignar a los usuarios acceso a todos los recursos de la cuenta.
* Una política de IAM con el rol de administrador sobre todos los servicios de gestión de cuentas, lo que permite a un usuario realizar tareas como invitar y eliminar usuarios, gestionar grupos de acceso, gestionar ID de servicio, gestionar ofertas de catálogo privadas y realizar un seguimiento de la facturación y del uso.
* El conjunto de permisos de superusuario para la infraestructura clásica
* Gestor de Cloud Foundry para todas las organizaciones


## ¿Qué diferencia hay entre un administrador de la cuenta y el propietario de la cuenta?
{: #owner-administrator}
{: faq}

Los propietarios de cuenta se asignan automáticamente como administrador de la cuenta para {{site.data.keyword.Bluemix_notm}} IAM. Como administrador de la cuenta, puede invitar a usuarios, asignar y gestionar el acceso para los usuarios, crear grupos de recursos, requerir MFA para todos los usuarios de la cuenta y crear instancias de servicio. Si desea convertir en administradores de la cuenta a otros usuarios de su cuenta, asígneles el siguiente acceso:

* Una política de IAM con el rol de administrador sobre todos los servicios habilitados para Identity and Access, lo que permite a un usuario crear instancias de servicio y asignar a los usuarios acceso a todos los recursos de la cuenta.
* Una política de IAM con el rol de administrador sobre todos los servicios de gestión de cuentas, lo que permite a un usuario realizar tareas como invitar a usuarios, gestionar grupos de acceso, gestionar ID de servicio, gestionar ofertas de catálogo privadas y realizar un seguimiento de la facturación y del uso.
* El conjunto de permisos de superusuario para la infraestructura clásica
* Gestor de Cloud Foundry para todas las organizaciones

## ¿Cómo se asigna acceso a la infraestructura y a los dispositivos?
{: #infrastructure-devices}
{: faq}

1. Vaya a **Gestionar** &gt; **Acceso (IAM)** y seleccione **Usuarios**.
2. Seleccione el nombre de un usuario.
3. Pulse **Infraestructura clásica**.
4. Asigne permisos desde la sección **Permisos**, asigne acceso a dispositivos desde la sección **Dispositivos** y asigne acceso a subredes VPN para los dispositivos sobre los que el usuario tiene acceso asignado desde la sección **Acceso VPN**.

## ¿Todos los usuarios de mi cuenta pueden ver todos los otros usuarios?
{: #users}
{: faq}

Un propietario de cuenta puede ver todos los usuarios de la cuenta y elegir la forma en que los usuarios pueden ver otros usuarios de la cuenta en la página Usuarios. Un propietario de cuenta puede ajustar el [valor de visibilidad de lista de usuarios](/docs/iam?topic=iam-userlistview#userlistview) en la página Valores seleccionando una de las siguientes opciones:

* **Vista no restringida**: todos los usuarios de la cuenta pueden ver todos los otros usuarios de la cuenta.
* **Vista restringida**: limita la capacidad de ver usuarios en la página Usuarios solo a aquellos a los que se ha otorgado acceso explícito, junto con aquellos que tienen visibilidad de otros usuarios a través de una organización de Cloud Foundry compartida o de una relación de la jerarquía de usuarios de la infraestructura clásica.


## ¿Tengo que asignar acceso a un usuario cuando lo invito a la cuenta?
{: #account-invite}
{: faq}

Sí. Debe signar acceso a un usuario mediante uno de estos tres sistemas de gestión de acceso:

* Una política de acceso de IAM sobre un recurso, grupo de recursos o servicios de gestión de la cuenta
* Un rol de Cloud Foundry para una organización y espacio
* El conjunto de permisos para la infraestructura clásica


## ¿Cómo puedo incorporar autenticación a mis apps web y móviles?
{: #appid}
{: faq}

Se utiliza IAM para gestionar el acceso a los servicios y recursos de {{site.data.keyword.cloud_notm}}. Con {{site.data.keyword.appid_full_notm}}, puede aumentar la seguridad de la nube añadiendo autenticación a sus apps web y móviles. Con unas pocas líneas de código puede proteger fácilmente sus apps y servicios nativos de la nube que se ejecutan en {{site.data.keyword.cloud_notm}}. ¿Está listo para empezar? [Consulte la documentación](/docs/services/appid?topic=appid-getting-started#getting-started). 
