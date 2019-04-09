---

copyright:

  years: 2017, 2019

lastupdated: "2019-04-02"

keywords: SoftLayer permissions, classic infrastructure access, classic infrastructure permission, migrated SoftLayer permissions, migrated permission access group

subcollection: iam

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:important: .important}
{:new_window: target="_blank"}

# Permisos de la infraestructura clásica
{: #infrapermission}

Cuando invita a un usuario a su cuenta, puede seleccionar entre tres conjuntos de permisos de la infraestructura clásica que asignan acceso masivo: Solo vista, Usuario básico, Superusuario.
{:shortdesc}

Cuando invita a alguien a la cuenta, solo usted, el propietario de la cuenta o un usuario con el permiso de la infraestructura clásica Gestionar usuario pueden ajustar los permisos del usuario. Si está asignando permisos y no es el propietario de la cuenta, solo podrá asignar el nivel de permisos o un subconjunto de permisos que ya tenga asignados. Un propietario de cuenta puede actualizar los permisos de otros usuarios de la cuenta para que puedan tener cualquier nivel de acceso.

Puede definir permisos adicionales después de que el usuario acepte la invitación. Por ejemplo, el conjunto inicial de permisos asignado en la invitación no otorga acceso a dispositivos. Por lo tanto, debe otorgar acceso a dispositivos después de que el usuario haya aceptado la invitación. Para obtener más información, consulte [Gestión de acceso de la infraestructura clásica](/docs/iam?topic=iam-mngclassicinfra#mngclassicinfra).

En el siguiente gráfico se muestra cómo se asignan los permisos de infraestructura clásica por usuario. Puede otorgar a cada usuario acceso a un dispositivo o servicio de infraestructura clásica seleccionando entre las opciones de permiso granular para personalizar cada acceso de usuario.

![Acceso de infraestructura clásica](images/ClassicIaaS.svg "Asignación de acceso de infraestructura clásica seleccionando un usuario, dispositivo o servicio y, finalmente, cualquier combinación de permisos granulares")



## Permisos migrados de la infraestructura clásica
{: #predefined}

Un conjunto de permisos de la infraestructura clásica para ver y gestionar información de facturación y para trabajar con casos de soporte se migran a grupos de acceso. A los usuarios de su cuenta a los que se asignó anteriormente estos permisos ahora se les asignará el grupo de acceso de permisos migrados correspondiente. Como resultado, los permisos de la infraestructura clásica se pueden gestionar directamente mediante políticas de acceso de IAM.

Estos grupos de acceso especiales incluyen todas las políticas de IAM adecuadas para conservar el comportamiento original de los permisos de la infraestructura clásica. Por ejemplo, para que un usuario siga viendo todas las actualizaciones de todos los usuarios en un caso de soporte, los grupos de acceso de permisos migrados correspondientes a los permisos de la infraestructura clásica de creación de incidencias incluyen una política de IAM adicional en el servicio de gestión de usuarios con el rol de visor asignado. Para obtener más información, consulte [Asignación de acceso de usuario para trabajar con casos de soporte](/docs/get-support?topic=get-support-access#access).

Puede seguir gestionando estos permisos migrados de la infraestructura clásica para los usuarios directamente desde IAM añadiéndolos o eliminándolos desde los grupos de acceso de los permisos migrados. Las políticas que tienen estos grupos de acceso están bloqueadas para conservar el comportamiento de acceso de sus miembros. Para mantener la facilidad de uso para los usuarios más recientes de IAM, evite suprimir estos grupos de acceso.

Una vez migrados los permisos de infraestructura clásica, debe dejar de utilizar dichos permisos. Consulte en la tabla siguiente todos los permisos migrados de la infraestructura clásica que ahora forman parte de los grupos de acceso de IAM.
{: important}

| Nombre grupo acceso permisos migrados | Acciones permitidas |
|----------|---------|
| Ver resumen de cuenta | Ver la página de resumen de cuenta y facturas y pagos |
| Obtener informe de conformidad | Solicitar informes de conformidad |
| Editar perfil de la empresa | Editar información del perfil de la empresa |
| Pagos de una sola vez | Realizar pagos de una sola vez en la cuenta del usuario |
| Actualizar detalles de pagos | Actualizar la formación de pagos mensuales recurrentes |
| Limitar restricción en caso de UE | Habilitar o inhabilitar la opción de soporte en UE que restringe los datos de casos de soporte a la Unión Europea  |
| Añadir casos y ver pedidos | Crear casos de soporte y ver todos los pedidos.  |
| Editar casos | Editar cualquier caso de soporte |
| Buscar casos | Buscar todos los casos de soporte, siempre que también se tenga asignado el permiso para ver casos |
| Ver casos | Ver todos los casos de soporte |
{: caption="Tabla 1. Grupos de acceso predefinidos" caption-side="top"}

Puede seguir gestionando los usuarios para los grupos de acceso. Sin embargo, probablemente encontrará útil crear nuevos grupos de acceso que incluyan una combinación de políticas de acceso para los [servicios de gestión de cuentas de IAM](/docs/iam?topic=iam-account-services#account-services). En la siguiente tabla se resaltan los detalles de una política de acceso de IAM que es equivalente a los grupos de acceso de permiso migrados, para que pueda volver a crear o incluso combinar estos permisos con otros en un nuevo grupo de acceso.


| Nombre grupo acceso permisos migrados | Descripción | Servicio de {{site.data.keyword.cloud_notm}} | Rol de IAM |
|-----------------------------------|-------------|-----------------------------------------|----------|
| Ver resumen de cuenta | Ver la página de resumen de cuenta y facturas y pagos  |  Facturación |  Visor    |
| Obtener informe de conformidad | Solicitar informes de conformidad | Facturación |    Visor |
| Editar perfil de la empresa | Editar información del perfil de la empresa | Facturación  | Operador |
| Actualizar detalles de pagos | Actualizar la formación de pagos mensuales recurrentes | Facturación   | Operador |
| Limitar restricción en caso de UE | Habilitar o inhabilitar la opción de soporte en UE que restringe los datos de casos de soporte a la Unión Europea  |   Facturación |   Operador   |
| Añadir casos y ver pedidos | Crear casos de soporte y ver todos los pedidos.  | Centro de soporte |   Editor   |
| Editar casos | Editar cualquier caso de soporte | Centro de soporte |   Editor |
| Buscar casos | Buscar todos los casos de soporte, siempre que también se tenga asignado el permiso para ver casos | Centro de soporte |  Visor |
| Ver casos | Ver todos los casos de soporte | Centro de soporte | Visor |
{: caption="Tabla 2. Acceso de permiso de infraestructura migrado correlacionado con roles de IAM" caption-side="top"}
