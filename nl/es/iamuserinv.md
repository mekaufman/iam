---

copyright:

  years: 2015, 2019
lastupdated: "2019-01-28"

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:tip: .tip}
{:note: .note}

# Invitación a usuarios
{: #iamuserinv}

Puede invitar a usuarios, cancelar invitaciones y volver a enviar una invitación pendiente a un usuario invitado. Además, puede invitar a un único usuario o a varios usuarios de una vez.    
{:shortdesc}

Para invitar a usuarios y gestionar invitaciones pendientes, debe ser propietario de la cuenta, gestor de la organización o un usuario con una política de acceso de IAM con el rol de editor o superior sobre el servicio de gestión de usuarios o bien debe tener permisos de la infraestructura para añadir usuarios.

## Configuración de una invitación
{: #invitations}

Complete los siguientes pasos para invitar a usuarios o para gestionar invitaciones de usuario en su cuenta:

1. En la barra de menús, pulse **Gestionar** &gt; **Acceso (IAM)** y seleccione **Usuarios**.
2. Pulse **Invitar a usuarios**.
3. Especifique la dirección de correo electrónico del usuario. Si está invitando a más de un usuario con una única invitación, a todos se les asigna el mismo acceso.
4. Añada una o varias de las opciones de acceso que gestionará. Debe asignar al menos una opción de acceso. Para las opciones de acceso adicionales que no desee añadir y configurar, se asigna el valor predeterminado **no access** (sin acceso). Es posible que vea una o todas las siguientes opciones de acceso, en función de las opciones que está autorizado a gestionar:

  * **Servicios**
  * **Acceso de Cloud Foundry**
  * **Acceso de la infraestructura clásica**.

  Para obtener más información, consulte [Asignación de acceso de usuario](/docs/iam?topic=iam-assignaccess#assignaccess).

Si determina que un usuario no necesita acceso, puede cancelar una invitación para cualquier usuario que se muestre en estado **Procesando** o **Pendiente** en la columna **Estado**. Si un usuario invitado no ha recibido una invitación, puede volver a enviar la invitación a cualquier usuario en estado **Pendiente**.

Si desea invitar a usuarios utilizando la interfaz de línea de mandatos (CLI), consulte el mandato [ibmcloud account user-invite](/docs/cli/reference/ibmcloud?topic=cloud-cli-ibmcloud_account_user_invite#ibmcloud_account_user_invite).
{: tip}

## Asignación de acceso de usuario desde una invitación
{: #assignaccess}

Puede asignar acceso a los usuarios a medida que los invita asignando políticas de IAM de {{site.data.keyword.Bluemix}}, acceso de Cloud Foundry y permisos de la infraestructura clásica. Según las opciones de acceso que esté autorizado a gestionar, puede invitar y proporcionar acceso a usuarios de la cuenta, grupos de recursos, organizaciones, espacios, instancias de servicio e infraestructura clásica. En las secciones siguientes se describen los tres tipos de acceso que se pueden asignar a un usuario invitado.

### Servicios
{: #invite_services}

Puede asignar acceso creando una política de acceso de IAM de {{site.data.keyword.Bluemix_notm}} inicial cuando invite a un nuevo usuario. En la sección Servicios, puede proporcionar a un usuario acceso a servicios de gestión de la cuenta, servicios en un grupo de recursos con acceso para gestionar el grupo de recursos o a un recurso individual en la cuenta.

Cuando el usuario acepte la invitación, puede asignarle acceso adicional. Consulte [Gestión del acceso a recursos](/docs/iam?topic=iam-iammanidaccser#iammanidaccser) para obtener detalles sobre la edición de políticas para añadir roles extra, asignar más acceso o eliminar una política para un usuario.

En función del servicio que seleccione al asignar la política, es posible que no vea todos los campos descritos en los procedimientos siguientes.
{: note}

#### Acceso a servicios de gestión de cuentas
{: #invite_acct_mgmt}

Para delegar algunas de sus responsabilidades como propietario de cuenta, puede proporcionar un acceso de usuario a los servicios de gestión de la cuenta. Por ejemplo, puede delegar la capacidad de ver información de facturación y uso, de invitar y eliminar usuarios, de gestionar grupos de acceso o de gestionar ID de servicio. Puede proporcionar acceso a todos los servicios de gestión de cuentas o solo a uno.

1. Desde la pantalla **Invitar a usuarios**, expanda la sección **Servicios**.
2. Seleccione que desea asignar acceso a **servicios de gestión de cuentas**
3. Seleccione **Todos los servicios de gestión de cuentas** o seleccione un servicio de gestión de cuentas específico.
4. Seleccione cualquier combinación de roles para asignar el acceso deseado.

#### Acceso a grupo de recursos
{: #invite_rgs}

Puede asignar acceso a todos los servicios dentro de un grupo de recursos o a un único tipo de servicio en un grupo de recursos.

1. Desde la pantalla **Invitar a usuarios**, expanda la sección **Servicios**.
2. Seleccione para asignar acceso a recursos en un **Grupo de recursos**.
3. Elija un grupo de recursos.
4. Elija un rol para el campo **Asignar acceso a un grupo de recursos** para permitir al usuario ver el grupo de recursos en la lista de recursos, editar el nombre del grupo de recursos o gestionar el acceso de usuario al grupo. Puede seleccionar **Sin acceso** si desea que el usuario solo tenga acceso al recurso que especifique y no al grupo en el que está organizado.
5. Seleccione un servicio dentro del grupo de recursos o seleccione proporcionar acceso a todos los servicios dentro del grupo seleccionado.
6. Seleccione cualquier combinación de roles para asignar el acceso deseado. Este acceso solo se aplica a los recursos que ha seleccionado para la política. No proporciona acceso al contenedor actual que es el grupo de recursos.

#### Acceso de recurso
{: #invite_resources}

Puede asignar acceso a un único recurso dentro de su cuenta en la instancia.

1. Desde la pantalla **Invitar a usuarios**, expanda la sección **Servicios**.
2. Seleccione para asignar acceso a un **Recurso**.
3. Seleccione un servicio.
4. Seleccione **Todas las regiones actuales** o una región específica, si se le solicita.
5. Seleccione **Todas las instancias de servicio actuales** o seleccione una instancia de servicio específica.
6. En función del servicio seleccionado, puede que vea los campos siguientes. Si no indica ningún valor en ellos, la política se asigna a nivel de instancia de servicio en lugar de a nivel de grupo.
    * **Tipo de recurso**: indique `grupo`.
    * **ID de recurso**: Especifique el nombre de su grupo.
7. Seleccione cualquier combinación de roles para asignar el acceso deseado.

Para obtener más información específica sobre los roles que se utilizan al asignar acceso, consulte [Acceso de IAM](/docs/iam?topic=iam-iamusermanrol#iamusermanrol).

### Acceso de Cloud Foundry
{: #invite_cf}

Cuando invita a nuevos usuarios, puede elegir añadirlos a una organización en la cuenta. Si añade el usuario a una organización, puede asignarle un rol de la organización. A continuación, seleccione proporcionar acceso al usuario invitado a uno o a todos los espacios de la organización seleccionada con un rol de espacio asignado.

1. Desde la pantalla **Invitar a usuarios**, expanda la sección **Acceso de Cloud Foundry**.
2. Seleccione una organización en la que añadir al usuario.
3. Seleccione un rol de organización para definir el nivel de acceso para la organización seleccionada.
4. Opcional: Seleccione **Añadir rol de organización** para especificar un rol extra.
5. Seleccione **Todas las regiones actuales** o una región específica.
6. Seleccione **Todos los espacios actuales** o un espacio específico.
7. Seleccione un rol de espacio para definir el nivel de acceso para los espacios seleccionados.
8. Opcional: Seleccione **Añadir rol de espacio** para especificar un rol extra.

Para obtener más información sobre los roles que se utilizan al asignar acceso, consulte [Roles de Cloud Foundry](/docs/iam?topic=iam-cfroles#cfroles).

Es posible añadir un rol de Cloud Foundry utilizando el mandato de CLI [ibmcloud account user-invite](/docs/cli/reference/ibmcloud?topic=cloud-cli-ibmcloud_account_user_invite#ibmcloud_account_user_invite), pero se debe utilizar la consola para asignar otros permisos o accesos.
{: tip}

### Acceso de infraestructura clásica
{: #invite_classicinfra}

Los permisos que se asignan se limitan automáticamente al subconjunto de permisos que posee. Se convierte en usuario padre de cualquier usuario que invite.

1. Desde la pantalla **Invitar a usuarios**, expanda la sección **Acceso de infraestructura clásica**.
2. Seleccione un conjunto de permisos para asignar permisos masivos predefinidos.

El acceso a dispositivos se otorga de forma separada después de añadir el usuario. Vaya a la opción de acceso **Infraestructura clásica** para un usuario en la consola.
{: note}

Para obtener información sobre la configuración del acceso para los usuarios después de que se añadan a su cuenta, consulte [Gestión del acceso de la infraestructura clásica](/docs/iam?topic=iam-mngclassicinfra#mngclassicinfra).

## Adición de usuarios de solo VPN
{: #add-vpn-only}

Como propietario de la cuenta o como usuario con permiso para gestionar la infraestructura clásica de usuario, puede añadir un usuario de solo VPN.

1. En la página **Usuarios**, pulse **Añadir usuario de solo VPN**.
2. Especifique los detalles de la información personal del usuario.
3. Pulse **Guardar**.
