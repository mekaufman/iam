---

copyright:

  years: 2019

lastupdated: "2019-05-13"

keywords: migrated permissions, SoftLayer account permissions, migrated permission access group, migrated classic infrastructure permissions

subcollection: iam

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:important: .important}
{:new_window: target="_blank"}


# Gestión de permisos migrados de cuenta de SoftLayer
{: #migrated_permissions}

Ahora los grupos de acceso incluyen un conjunto migrado de permisos de cuenta de SoftLayer para ver y gestionar información de facturación y para trabajar con casos de soporte. A los usuarios de su cuenta a los que se asignó anteriormente estos permisos ahora se les asignará el grupo de acceso de permisos migrados correspondiente. Como resultado, los permisos se pueden gestionar directamente mediante grupos de acceso de IAM.
{:shortdesc}

Estos grupos de acceso especiales incluyen todas las políticas de IAM adecuadas para conservar el comportamiento original de los permisos de cuenta de SoftLayer. Por ejemplo, para que un usuario siga viendo todas las actualizaciones de todos los usuarios en un caso de soporte, los grupos de acceso de permisos migrados correspondientes a los permisos de la cuenta de SoftLayer con creación de incidencias incluyen una política de IAM adicional en el servicio de gestión de usuarios con el rol de visor asignado. Para obtener más información, consulte [Asignación de acceso de usuario para trabajar con casos de soporte](/docs/get-support?topic=get-support-access#access).

Puede seguir gestionando estos permisos migrados de la infraestructura clásica para los usuarios directamente desde IAM añadiéndolos o eliminándolos desde los grupos de acceso de los permisos migrados. Las políticas que tienen estos grupos de acceso están bloqueadas para conservar el comportamiento de acceso de sus miembros. Para mantener la facilidad de uso para los usuarios más recientes de IAM, evite suprimir estos grupos de acceso.

Una vez migrados los permisos de infraestructura clásica, debe dejar de utilizar dichos permisos. Consulte en la tabla siguiente todos los permisos migrados de la infraestructura clásica que ahora forman parte de los grupos de acceso de IAM.
{: important}

| Nombre grupo acceso permisos migrados | Acciones permitidas |
|----------|---------|
| Ver resumen de cuenta | Ver la página de resumen de cuenta y facturas y pagos. |
| Obtener informe de conformidad | Solicitar informes de conformidad. |
| Editar perfil de la empresa | Editar información del perfil de la empresa. |
| Pagos de una sola vez | Realizar pagos únicos en la cuenta del usuario. |
| Actualizar detalles de pagos | Actualizar la información de pago mensual recurrente. |
| Limitar restricción en caso de UE | Habilitar o inhabilitar la opción de soporte en UE que restringe los datos de casos de soporte a la Unión Europea.  |
| Añadir casos y ver pedidos | Crear casos de soporte y ver todos los pedidos.  |
| Editar casos | Editar cualquier caso de soporte. |
| Buscar casos | Buscar todos los casos de soporte si también se ha asignado el permiso para ver casos. |
| Ver casos | Ver todos los casos de soporte. |
{: caption="Tabla 1. Grupos de acceso predefinidos" caption-side="top"}

