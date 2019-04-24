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

# Gestión de políticas de acceso de ID de servicio
{: #serviceidpolicy}

Al crear un ID de servicio, puede asignar políticas de servicio para dicho ID de servicio para controlar el nivel de acceso permitido cuando se utiliza para autenticarse con los servicios. Puede actualizar estas políticas de acceso asignadas en cualquier momento cambiando una política existente, suprimiendo una política o asignando una nueva.
{:shortdesc}

Si suprime o edita una política existente para un ID de servicio actualmente en uso, puede causar una interrupción de servicio.
{: note}

## Asignación de nuevos accesos
{: #access_new}

Para asignar acceso a todos los recursos de un grupo de recursos o solo a un servicio del grupo, complete los siguientes pasos:

1. En la barra de menús, pulse **Gestionar** &gt; **Acceso (IAM)** y seleccione **ID de servicio**.
2. Seleccione el ID de servicio desde la tabla para la que desea asignar una política de servicios.
3. Pulse **Políticas de acceso**.
4. Pulse **Asignar acceso**.
5. Seleccione **Asignar por grupo de recursos**.
6. Seleccione un grupo de recursos.
7. Seleccione un rol para el campo **Asignar acceso a un grupo de recursos**. Esta opción permite al usuario visualizar el grupo de recursos en su lista de recursos, editar el nombre del grupo de recursos o gestionar el acceso de usuario al grupo. Puede seleccionar **Sin acceso** si desea que el usuario solo tenga acceso al recurso que especifique y no al grupo al que está asignado.
8. Seleccione un servicio dentro del grupo de recursos o seleccione proporcionar acceso a todos los servicios dentro del grupo seleccionado.
9. Elija cualquier combinación de roles para asignar el acceso deseado para el usuario. Este acceso solo se aplica a los recursos que ha seleccionado para la política. No proporciona acceso al contenedor actual que es el grupo de recursos.
10. Seleccione **Asignar**.

Para asignar acceso a un recurso individual en la cuenta, complete los siguientes pasos:

1. En la barra de menús, pulse **Gestionar** &gt; **Acceso (IAM)** y seleccione **ID de servicio**.
2. Seleccione el ID de servicio desde la tabla para la que desea asignar una política de servicios.
3. 3. Pulse **Políticas de acceso**.
4. Pulse **Asignar acceso**.
5. Seleccione **Asignar por recurso**.
6. Seleccione un servicio.
7. Seleccione **Todas las regiones actuales** o una región específica, si se le solicita.
8. Seleccione **Todas las instancias de servicio actuales** o seleccione una instancia de servicio específica.
9. En función del servicio seleccionado, puede que vea los campos siguientes. Si no indica ningún valor en ellos, la política se asigna a nivel de instancia de servicio en lugar de a nivel de grupo.
    * **Tipo de recurso**: indique **grupo**.
    * **ID de recurso**: Especifique el nombre de su grupo.
10. Elija cualquier combinación de roles para asignar el acceso deseado para el usuario.
11. Seleccione **Asignar**.

Para asignar acceso a servicios de gestión de cuentas individuales o a todos los servicios de gestión de cuentas, siga los pasos siguientes:

1. En la barra de menús, pulse **Gestionar** &gt; **Acceso (IAM)** y seleccione **ID de servicio**.
2. Seleccione el ID de servicio desde la tabla para la que desea asignar una política de servicios.
3. Pulse **Políticas de acceso**.
4. Pulse **Asignar acceso**.
5. Seleccione que desea asignar acceso a **Servicios de gestión de cuentas**
6. Seleccione **Todos los servicios de gestión de cuentas** o seleccione un servicio de gestión de cuentas específico.
7. Seleccione cualquier combinación de roles para asignar el acceso deseado.

Es posible que reciba un mensaje que indica que existe una política para los detalles que ha seleccionado. Si se crea una política con los detalles y roles exactos, se le solicitará realizar cambios en la nueva política puesto que las políticas duplicadas no están permitidas. Si crea una política con los mismos detalles pero con una asignación de roles distinta como una política existente, se le solicitará revisar y actualizar la política existente con las asignaciones de roles que desea asignar.
{: tip}

## Edición de accesos existentes
{: #access_edit}

Para editar una política existente:

1. En la barra de menús, pulse **Gestionar** &gt; **Acceso (IAM)** y seleccione **ID de servicio**.
2. Seleccione el ID de servicio de la tabla para la que desea editar una política de servicios.
3. Pulse **Políticas de acceso**.
4. Identifique la fila de la política que desea editar y seleccione **Editar política** en el menú **Acciones** ![Icono Lista de acciones](../icons/action-menu-icon.svg).
5. Realice los cambios y, a continuación, guarde la política.

Para actualizar una política de servicios utilizando la CLI, puede utilizar el mandato [ibmcloud iam service-policy-update](/docs/cli/reference/ibmcloud?topic=cloud-cli-ibmcloud_iam_user_policy_update#ibmcloud_iam_service_policy_update).
```
ibmcloud iam service-policy-update SERVICE_ID POLICY_ID [-v, --version VERSION] {--file JSON_FILE | [-r, --roles ROLE_NAME1,ROLE_NAME2...] [--service-name SERVICE_NAME] [--service-instance SERVICE_INSTANCE] [--region REGION] [--resource-type RESOURCE_TYPE] [--resource RESOURCE] [--resource-group-name RESOURCE_GROUP_NAME] [--resource-group-id RESOURCE_GROUP_ID]} [-f, --force]",
```
{: codeblock}

Cuando edite el acceso de un ID de servicio, es posible que reciba un mensaje acerca de no permitir las políticas duplicadas. Si está editando una política existente y los cambios que realiza entran en conflicto con el acceso que ya se ha asignado, puede modificar la política que está editando para proporcionar un acceso distinto o puede ir a la política existente con la que se encuentra en conflicto para revisarla y realizar cambios si es necesario. Es posible que desee suprimir la política que está editando si existe una política duplicada que cumple con sus necesidades.
{: tip}

## Eliminación de acceso
{: #access_remove}

Para eliminar una política existente:

1. En la barra de menús, pulse **Gestionar** &gt; **Acceso (IAM)** y seleccione **ID de servicio**.
2. Seleccione el ID de servicio de la tabla para la que desea suprimir una política de servicios.
3. Pulse **Políticas de acceso**. 
4. Identifique la fila de la política que desea suprimir y seleccione **Eliminar** en el menú **Acciones** ![Icono Lista de acciones](../icons/action-menu-icon.svg).
5. Revise los detalles de la política que va a eliminar y luego pulse **Eliminar** para confirmar.

Para suprimir una política de servicios utilizando la CLI, puede utilizar el mandato [ibmcloud iam service-policy-delete](/docs/cli/reference/ibmcloud?topic=cloud-cli-ibmcloud_iam_user_policy_update#ibmcloud_iam_service_policy_delete).
```
ibmcloud iam service-policy-delete SERVICE_ID POLICY_ID [-f, --force]
```
{: codeblock}
