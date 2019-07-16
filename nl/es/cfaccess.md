---

copyright:

  years: 2017, 2019

lastupdated: "2019-04-02"

keywords: Cloud Foundry roles, Cloud Foundry access, auditor, manager, developer, billing manager

subcollection: iam

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:tip: .tip}
{:note: .note}

# Acceso de Cloud Foundry
{: #cfaccess}

Actualmente, no todos los servicios se pueden gestionar utilizando Cloud IAM. Puede seguir utilizando los roles de Cloud Foundry para acceder a estas instancias de servicio. Los usuarios se añaden a la organización y el espacio a los que pertenece la instancia, con un rol de Cloud Foundry asignado.
{:shortdesc}

En el siguiente gráfico se describe cómo se relacionan las organizaciones, los espacios y los roles de Cloud Foundry en una cuenta. Una cuenta puede tener varios usuarios, organizaciones y espacios. A cada usuario se le pueden asignar tantas organizaciones y espacios como sean necesarios, y cuando se asignan a una organización y espacio, puede establecer el nivel de acceso para trabajar en cada uno asignando un rol de Cloud Foundry.

![Acceso mediante espacios y organizaciones de Cloud Foundry en una cuenta](images/cf-diagram.svg "Cómo funciona el acceso de una cuenta utilizando roles, espacios y organizaciones de Cloud Foundry")

## Roles de Cloud Foundry
{: #cfroles}

Los roles de Cloud Foundry otorgan acceso a las organizaciones y espacios dentro de la cuenta. Los roles de Cloud Foundry no habilitan permisos de usuario para completar acciones dentro del contexto de un servicio en la cuenta.

El acceso de Cloud Foundry se asigna añadiendo un usuario a una organización y espacio y, a continuación, asignando un rol de organización y un rol de espacio. En función del tipo de rol que se asigna, dicho usuario puede completar acciones específicas para las instancias de servicio que se añaden a un espacio determinado.

![Acceso de Cloud Foundry](images/CF.svg "Asignación de acceso de usuario a una organización y espacio de Cloud Foundry")

Los siguientes roles se pueden asignar a nivel de organización:

| Rol de organización | Permisos |
|-------------------|-------------|
|Gestor | Los gestores de organización pueden crear, ver, editar o suprimir espacios dentro de la organización, ver la cuota y el uso de la organización, invitar a usuarios a la organización, gestionar quién tiene acceso a la organización y sus roles en la organización, y gestionar dominios personalizados para la organización. |
|Gestor de facturación | Los gestores de facturación pueden ver la información de uso de tiempo de ejecución y servicio para la organización de la página Uso.  |
|Auditor | Los auditores de organización pueden ver el contenido de aplicación y servicio en la organización. Los auditores también pueden ver los usuarios de la organización y sus roles asignados, y la cuota para la organización. |
{:caption="Tabla 1. Permisos y roles de organización" caption-side="top"}

Los siguientes roles se pueden asignar a nivel de espacio:

| Rol de espacio | Permisos |
|------------|-------------|
|Gestor | Los gestores de espacios pueden añadir usuarios existentes y gestionar roles dentro del espacio. Los gestores de espacios también pueden ver el número de instancias, enlaces de servicio y uso de recursos para cada aplicación en el espacio. |
|Desarrollador | Los desarrolladores de espacios pueden crear, suprimir y gestionar aplicaciones y servicios dentro del espacio. Algunas de las tareas de gestión incluyen el desarrollo de apps, el inicio o la detención de apps, el cambio de nombre de una app, la supresión de una aplicación, el enlace o desenlace de un servicio con una aplicación, ver el número o instancias, enlaces de servicio y uso de recursos para cada aplicación en el espacio. Además, el desarrollador de espacios puede asociar un URL interno o externo con una aplicación en el espacio.   |
|Auditor | Los auditores del espacio tienen acceso de solo lectura a toda la información sobre el espacio, como la información sobre el número de instancias, enlaces de servicio y uso de recursos para cada aplicación en el espacio. |
{:caption="Tabla 2. Permisos y roles de espacio" caption-side="top"}

Los usuarios que tienen asignado el rol de espacio de gestor o desarrollador pueden acceder a la variable de entorno VCAP_SERVICES. Sin embargo, un usuario que tienen asignado el rol de auditor no puede acceder a VCAP_SERVICES.
{: note}
