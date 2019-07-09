---

copyright:

  years: 2019

lastupdated: "2019-06-24"

keywords: migrated permissions, SoftLayer account permissions, migrated permission access group, migrated classic infrastructure permissions

subcollection: iam

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:important: .important}
{:new_window: target="_blank"}
{:note: .note}


# Gestión de permisos migrados de cuenta de SoftLayer
{: #migrated_permissions}

Puede utilizar grupos de acceso de permisos migrados para administrar un conjunto de permisos de la infraestructura clásica (SoftLayer) para gestionar la información de facturación y trabajar con casos de soporte. Los grupos de acceso contienen un conjunto de usuarios e ID de servicio que tienen el mismo acceso. A los usuarios de su cuenta de SoftLayer a los que se asignaron anteriormente permisos de cuenta y de soporte, ahora se les asignará el grupo de acceso de permisos migrados correspondiente. Como resultado, los permisos se pueden gestionar directamente mediante grupos de acceso de IAM.
{:shortdesc}

Estos grupos de acceso especiales incluyen todas las políticas de IAM adecuadas para conservar el comportamiento original de los permisos de cuenta de SoftLayer. Por ejemplo, para que un usuario siga viendo todas las actualizaciones de todos los usuarios en un caso de soporte, los grupos de acceso de permisos migrados correspondientes a los permisos de la cuenta de SoftLayer con creación de incidencias incluyen una política de IAM adicional en el servicio de gestión de usuarios con el rol de visor asignado. Para obtener más información, consulte [Asignación de acceso de usuario para trabajar con casos de soporte](/docs/get-support?topic=get-support-access#access).

Una vez migrados los permisos de infraestructura clásica, debe dejar de utilizar dichos permisos, así como la CLI o la API de SoftLayer para gestionarlos. Consulte la tabla siguiente para ver los permisos migrados de la infraestructura clásica que ahora forman parte de los grupos de acceso de IAM.
Solo se crean grupos de acceso para los permisos que ya estén asignados a usuarios, por lo es posible que observe un subconjunto de los grupos de acceso de su cuenta enumerados en la tabla siguiente.
{: note}

Puede seguir gestionando estos permisos migrados de la infraestructura clásica para los usuarios directamente desde IAM añadiendo y eliminando usuarios de los grupos de acceso. Las políticas de los grupos de acceso están bloqueadas para conservar el comportamiento de acceso de sus miembros. Sin embargo, probablemente encontrará útil crear nuevos grupos de acceso que incluyan una combinación de políticas de acceso para los [servicios de gestión de cuentas](/docs/iam?topic=iam-account-services#account-services).
En la tabla siguiente se describen los detalles de una política de acceso de IAM que incluye el permiso del grupo de acceso de permisos migrados para que pueda volver a crear o incluso combinar estos permisos con otros de un nuevo grupo de acceso. 

| Nombre grupo acceso permisos migrados | Descripción | Servicio de gestión de cuentas | Rol de IAM |
|-----------------------------------|-------------|-----------------------------------------|----------|
| Ver resumen de cuenta | Ver la página de resumen de cuenta y facturas y pagos.  |  Facturación |  Visor    |
| Obtener informes de conformidad | Solicitar informes de conformidad. | Facturación |    Visor |
| Editar perfil de la empresa | Editar información del perfil de la empresa. | Facturación  | Operador |
| Actualizar detalles de pagos | Actualizar la información de pago mensual recurrente. | Facturación   | Operador |
| Limitar restricción en caso de UE | Habilitar o inhabilitar la opción de soporte en UE para restringir los datos de casos de soporte a la Unión Europea.  |   Facturación |   Operador   |
| Añadir casos y ver pedidos | Crear casos de soporte y ver todos los pedidos.  | Centro de soporte |   Editor   |
| Editar casos | Editar cualquier caso de soporte. | Centro de soporte |   Editor |
| Buscar casos | Buscar todos los casos de soporte si también se ha asignado el permiso para ver casos. | Centro de soporte |  Visor |
| Ver casos | Ver todos los casos de soporte. | Centro de soporte y gestión de usuarios | Visor, visor |
{: caption="Tabla 1. Permisos de infraestructura migrados que se correlacionan con roles de IAM" caption-side="top"}

Para el acceso para ver casos, cree dos políticas independientes con el rol de visor para los servicios de gestión de usuarios y del centro de soporte. La política sobre el servicio de gestión de usuarios garantiza que el usuario pueda ver todos los casos de la cuenta independientemente de quién los haya abierto. Sin la política sobre el servicio de gestión de usuarios, si el propietario de la cuenta ha restringido la capacidad de los usuarios de poder ver a otros usuarios de la cuenta, la vista de casos del usuario se podría ver limitada únicamente a aquellos que haya abierto él mismo.
{: note}

## Asignación de nuevas políticas de acceso de IAM para permisos migrados
{: #migrated-permissions-iam}

Para volver a crear los permisos migrados que están disponibles en cada grupo de acceso, puede asignar políticas a usuarios individuales o crear nuevos grupos de acceso en la cuenta. La ventaja de crear un nuevo grupo de acceso es que puede optar por combinar un conjunto de permisos para un grupo de acceso en lugar de gestionar un conjunto de grupos de acceso con el ámbito granular del acceso establecido para cada uno de ellos. Para este ejemplo, los pasos describen cómo crear un nuevo grupo de acceso y asignar una política de acceso equivalente para ver el resumen de cuenta y todos los casos de soporte. 

Es posible que al volver a crear estos permisos mediante la asignación de nuevas políticas de acceso de IAM para los servicios de gestión de cuentas se incluyan permisos adicionales al permiso individual que está disponible en el grupo de acceso de permisos migrados. Por ejemplo, si asigna a un usuario el rol de visor sobre el servicio Facturación, dicho usuario podrá hacer más que simplemente ver el resumen de cuenta. Para obtener una lista completa de las acciones permitidas para cada rol, consulte
[Asignación de acceso a servicios de gestión de usuarios](/docs/iam?topic=iam-account-services#account-services).
{: important}

Para crear un grupo de acceso, complete los pasos siguientes:

1. En la barra de menús, pulse **Gestionar** &gt; **Acceso (IAM)** y seleccione **Grupos de acceso**.
2. Pulse **Crear**.
3. Especifique un nombre y una descripción opcional para el grupo y pulse **Crear**.
4. Pulse **Añadir usuarios** en el separador **Usuarios**.
3. Seleccione los usuarios de la lista que desea añadir y pulse **Añadir a grupo**. Puede realizar la misma acción desde el separador **ID de servicio** si desea añadir ID de servicio al grupo. 

Tras configurar el grupo con usuarios e ID de servicio, asigne el acceso al grupo. Recuerde que cualquier política que establezca para el grupo se aplicará a todos los miembros del grupo. 

1. Pulse el separador **Políticas de acceso**.
2. Pulse **Asignar acceso**.
3. Seleccione la opción **Asignar acceso a servicios de gestión de cuentas**.
4. Seleccione el servicio **Facturación**.
5. Seleccione el rol **Visor**.
6. Pulse **Asignar**.
7. Pulse **Asignar acceso** para asignar una segunda política de acceso para poder ver casos de soporte. 
8. Elija **Asignar acceso a servicios de gestión de cuentas**.
9. Seleccione el servicio **Centro de soporte**.
10. Seleccione el rol **Visor**.
11. Pulse **Asignar**.
12. Pulse **Asignar acceso** para asignar una tercera política de acceso para poder ver todos los casos de soporte independientemente de cómo haya configurado el propietario de la cuenta el valor de visibilidad de usuarios de la cuenta. 
13. Seleccione la opción **Asignar acceso a servicios de gestión de cuentas**.
14. Seleccione el servicio **Gestión de usuarios**.
15. Seleccione el rol **Visor**.
16. Pulse **Asignar**.

Ahora hay tres políticas asignadas al grupo: 

* Una política para ver el resumen de la cuenta y todas las demás acciones asociadas al rol de visor en el servicio Facturación. 
* Una política para ver y buscar casos de soporte en la cuenta. 
* Una política para ver todos los usuarios de la cuenta y todas las demás acciones asociadas al rol de visor en el servicio Gestión de usuarios. 

