---

copyright:

  years: 2018, 2019
lastupdated: "2019-01-30"

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:tip: .tip}
{:note: .note}


# Configuración de grupos de acceso
{: #groups}

Se puede crear un grupo de acceso para organizar un conjunto de usuarios e ID de servicio en una sola entidad, lo que le facilita la asignación de acceso. Puede asignar una única política al grupo en lugar de asignar el mismo acceso varias veces por usuario individual o ID de servicio.
{:shortdesc}

Para gestionar o crear nuevos grupos de acceso, debe ser el propietario de la cuenta, administrador o editor en el servicio IAM Access Groups en la cuenta o el administrador o editor asignado para todos los servicios de gestión de la cuenta. Además, se puede asignar a un administrador o editor acceso para gestionar un grupo individual creando una política de acceso donde el recurso es el ID del grupo de acceso. Para obtener más información sobre las políticas de acceso y los roles correspondientes al servicio IAM Access Groups, consulte [Acceso de IAM](/docs/iam?topic=iam-userroles#userroles).

Para facilitar aún más la asignación y gestión de accesos, puede configurar grupos de recursos para organizar el conjunto de recursos al que desea que un grupo de usuarios tenga acceso. Cuando el grupo de recursos esté configurado, podrá asignar una política otorgando acceso a todos los recursos del grupo, en lugar de crear políticas de acceso para instancias de servicio individuales de su cuenta. 
{: tip}

## Creación de un grupo de acceso
{: #create_ag}

Para crear un grupo de acceso, complete los pasos siguientes:

1. En la barra de menús, pulse **Gestionar** &gt; **Acceso (IAM)** y seleccione **Grupos de acceso**.
2. Pulse **Crear**.
3. Especifique un nombre y una descripción opcional para el grupo y pulse **Crear**.

A continuación, siga configurando el grupo añadiendo usuarios o ID de servicio:

1. Seleccione el nombre del grupo al que desea añadir.
2. Pulse **Añadir usuarios** en el separador **Usuarios**. 
3. Seleccione los usuarios de la lista que desea añadir y pulse **Añadir a grupo**.
4. Para añadir ID de servicio al grupo pulse el separador **ID de servicio** y luego **Añadir ID de servicio**.
5. Seleccione los ID de la lista que desea añadir y pulse **Añadir grupo**.

Puede suprimir un grupo seleccionando la opción **Eliminar grupo**. Cuando elimina un grupo de la cuenta, también elimina todos los usuarios e ID de servicio del grupo y todo el acceso asignado al grupo.
{: note}

Para crear un grupo de acceso utilizando la CLI, puede utilizar el mandato [ibmcloud iam access-group-create](/docs/cli/reference/ibmcloud?topic=cloud-cli-ibmcloud_commands_iam#ibmcloud_iam_access_group_create).
```
ibmcloud iam access-group-create GROUP_NAME [-d, --description DESCRIPTION]
```
{: codeblock}


## Asignación de acceso a un grupo
{: #access_ag}

Después de configurar el grupo con usuarios e ID de servicio, puede asignar una política de acceso común al grupo. Recuerde que cualquier política que establezca para el grupo se aplica a todas las entidades del mismo.

1. En la barra de menús, pulse **Gestionar** &gt; **Acceso (IAM)** y seleccione **Grupos de acceso**.
2. Seleccione el nombre del grupo al que desea asignar el acceso. 
3. Pulse **Políticas de acceso**.
4. Pulse **Asignar acceso**. 
5. Elija asignar acceso por recursos en un grupo de recursos, en recursos individuales disponibles en la cuenta o en servicios de gestión de la cuenta.

Para crear una política de grupo de acceso utilizando la CLI, puede utilizar el mandato [ibmcloud iam access-group-policy-create](/docs/cli/reference/ibmcloud?topic=cloud-cli-ibmcloud_commands_iam#ibmcloud_iam_access_group_policy_create).
```
ibmcloud iam access-group-policy-create GROUP_NAME {-f, --file @JSON_FILE | --roles ROLE_NAME1,ROLE_NAME2... [--service-name SERVICE_NAME] [--service-instance SERVICE_INSTANCE] [--region REGION] [--resource-type RESOURCE_TYPE] [--resource RESOURCE] [--resource-group-name RESOURCE_GROUP_NAME] [--resource-group-id RESOURCE_GROUP_ID]}
```
{: codeblock}


