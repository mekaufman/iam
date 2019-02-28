---

copyright:

  years: 2017, 2019

lastupdated: "2019-01-28"

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:tip: .tip}
{:note: .note}

# Gestión del acceso a los recursos
{: #iammanidaccser}

Para gestionar el acceso o asignar nuevos accesos a usuarios utilizando las políticas de IAM, debe ser el propietario de la cuenta, el administrador de todos los servicios de la cuenta o el administrador asignado para un servicio o instancia de servicio particular. Para obtener más información sobre las políticas de acceso y los roles, consulte [Acceso de IAM](/docs/iam?topic=iam-userroles#userroles).
{:shortdesc} 

## Edición de accesos existentes
{: #edit_existing}

1. En la barra de menús, pulse **Gestionar** &gt; **Acceso (IAM)** y seleccione **Usuarios**.
2. Seleccione el nombre del usuario al que desea asignar el acceso.
3. En la fila correspondiente a la política que desea editar, seleccione el menú **Acciones** ![Icono Lista de acciones](../icons/action-menu-icon.svg) y pulse **Editar política**.
4. Edite la política.
5. Pulse **Guardar**.

Para actualizar una política de usuario utilizando la CLI, puede utilizar el mandato [ibmcloud iam user-policy-update](/docs/cli/reference/ibmcloud?topic=cloud-cli-ibmcloud_commands_iam#ibmcloud_iam_user_policy_update).
```
ibmcloud iam user-policy-update USER_NAME POLICY_ID [-v, --version VERSION] {-f, --file JSON_FILE | [--roles ROLE_NAME1,ROLE_NAME2...] [--service-name SERVICE_NAME] [--service-instance SERVICE_INSTANCE] [--region REGION] [--resource-type RESOURCE_TYPE] [--resource RESOURCE] [--resource-group-name RESOURCE_GROUP_NAME] [--resource-group-id RESOURCE_GROUP_ID]}
```
{: codeblock}

Cuando edite el acceso de un usuario o grupo, es posible que reciba un mensaje acerca de no permitir las políticas duplicadas. Si está editando una política existente y los cambios que realiza entran en conflicto con el acceso que ya se ha asignado, puede modificar la política que está editando para proporcionar un acceso distinto o puede ir a la política existente con la que se encuentra en conflicto para revisarla y realizar cambios si es necesario. Es posible que desee suprimir la política que está editando si ya existe una política duplicada que cumple con sus necesidades.
{: note}

## Asignación de nuevos accesos
{: #assign_new_access}

Puede asignar acceso a recursos mediante dos tipos de política: 

* Acceso a recursos dentro de un grupo de recursos, incluida la opción de seleccionar uno o todos
* Acceso a recursos de la cuenta, incluida la opción de seleccionar un tipo o todos ellos

Si desea habilitar el acceso completo de administrador para un usuario para que realice tareas de [gestión de la cuenta](/docs/iam?topic=iam-account-services#account-services), como invitar y eliminar usuarios, ver información de facturación y de uso, gestionar ID de servicio, gestionar grupos de acceso, gestionar acceso de usuarios y acceder a todos los recursos de la cuenta, debe crear dos políticas: una sobre **Todos los servicios habilitados para Identity and Access** con el rol de administrador y una sobre **Todos los servicios de gestión de cuentas** con el rol de administrador.
{: tip}

### Acceso a recursos dentro de un grupo de recursos 
{: #access_to_resources}

Para asignar acceso a todos los recursos de un grupo de recursos o solo a un servicio del grupo, complete los siguientes pasos:

1. En la barra de menús, pulse **Gestionar** &gt; **Acceso (IAM)** y seleccione **Usuarios**.
2. En la fila correspondiente al usuario al que desea asignar acceso, seleccione el menú **Acciones** ![Icono Lista de acciones](../icons/action-menu-icon.svg) y pulse **Asignar acceso**.
3. Seleccione **Asignar acceso dentro de un grupo de recursos**.
4. Seleccione un grupo de recursos.
5. Elija un rol para el campo **Asignar acceso a un grupo de recursos** para permitir al usuario ver el grupo de recursos en su lista de recursos, editar el nombre del grupo de recursos o gestionar el acceso de usuario al grupo. Puede seleccionar **Sin acceso** si desea que el usuario solo tenga acceso al recurso que especifique y no al grupo en el que está organizado.
6. Seleccione un servicio dentro del grupo de recursos o seleccione proporcionar acceso a todos los servicios dentro del grupo seleccionado.
7. Elija cualquier combinación de roles para asignar el acceso deseado para el usuario. Este acceso solo se aplica a los recursos que ha seleccionado para la política. No proporciona acceso al contenedor actual que es el grupo de recursos.
8. Pulse **Asignar**.

### Acceso a recursos
{: #resourceaccess}

Para asignar acceso a un recurso individual en la cuenta o acceso a todos los recursos de la cuenta, complete los siguientes pasos: 

1. En la barra de menús, pulse **Gestionar** &gt; **Acceso (IAM)** y seleccione **Usuarios**.
2. En la fila correspondiente al usuario al que desea asignar acceso, seleccione el menú **Acciones** ![Icono Lista de acciones](../icons/action-menu-icon.svg) y pulse **Asignar acceso**.
3. Seleccione **Asignar acceso a recursos**.
4. Seleccione un servicio o seleccione **Todos los servicios habilitados para identidad y acceso**.
5. Seleccione **Todas las regiones actuales** o una región específica, si se le solicita. 
6. Seleccione **Todas las instancias de servicio actuales** o seleccione una instancia de servicio específica.
7. En función del servicio seleccionado, puede que vea los campos siguientes. Si no indica ningún valor en ellos, la política se asigna a nivel de instancia de servicio en lugar de a nivel de grupo. 
    * **Tipo de recurso**: indique **grupo**.
    * **ID de recurso**: Especifique el nombre de su grupo.
8. Elija cualquier combinación de roles para asignar el acceso deseado para el usuario.
9. Pulse **Asignar**.

## Eliminación de acceso
{: #removing_access}

1. En la barra de menús, pulse **Gestionar** &gt; **Acceso (IAM)** y seleccione **Usuarios**.
2. Seleccione el nombre de usuario al que desea eliminar el acceso.
3. En el separador **Políticas de acceso**, seleccione el menú **Acciones** ![Icono Lista de acciones](../icons/action-menu-icon.svg) en la fila correspondiente a la política que desea eliminar y pulse **Eliminar**.  
4. Revise los detalles de la política de usuario que está a punto de eliminar y confirme pulsando **Eliminar**.

Para eliminar una política de usuario utilizando la CLI, puede utilizar el mandato [ibmcloud iam user-policy-delete](/docs/cli/reference/ibmcloud?topic=cloud-cli-ibmcloud_iam_user_policy_delete#ibmcloud_iam_user_policy_delete).
```
ibmcloud iam user-policy-delete USER_ID POLICY_ID [-f, --force]
```
{: codeblock}

## Revisión de su acceso asignado
{: #review_your_access}

Si necesita revisar su acceso asignado en una cuenta a la que ha sido añadido, complete los siguientes pasos:

1. En la barra de menús, pulse **Gestionar** &gt; **Acceso (IAM)** y seleccione **Usuarios**.
3. Seleccione su nombre.
4. Revise su acceso asignado en la sección **Políticas de acceso**.

Si necesita más acceso, debe ponerse en contacto con el propietario de la cuenta para actualizar su acceso o con el administrador del servicio o la instancia de servicio para que actualice la política de acceso de Cloud IAM.
