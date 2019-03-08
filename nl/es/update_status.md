---

copyright:
  years: 2018, 2019
lastupdated: "2019-01-28"

keywords: user state, user status, change user status, update user status

subcollection: iam

---


{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:codeblock: .codeblock}
{:screen: .screen}
{:tip: .tip}
{:note: .note}

# Actualización del estado de un usuario
{: #status}

El estado asignado de un usuario depende de si el usuario ha aceptado su invitación para unirse a la cuenta, si es un usuario de solo VPN o de si el administrador del usuario ha establecido el usuario como un usuario inhabilitado de la infraestructura clásica.
{:shortdesc}

Si tiene el acceso siguiente, puede actualizar el estado de otro usuario:

  * Una política de IAM con el rol de editor o superior en el servicio de gestión de usuarios.
  * Es un antecesor en la jerarquía de la infraestructura clásica para el usuario y tiene asignado el permiso de la infraestructura clásica de gestión de usuarios

Para obtener más información sobre los tipos de estados de usuario, consulte [Estados de usuario](/docs/iam?topic=iam-user_status#user_status).

## Opciones para cambiar el estado de un usuario
{: #status_options}

Puede elegir entre las opciones siguientes para actualizar el estado de un usuario:

<dl>
<dt>Activo</dt>
<dd>El usuario tiene acceso completo a la consola de {{site.data.keyword.cloud_notm}} en función de sus políticas de acceso asignadas y los permisos de la infraestructura clásica.</dd>
<dt>Infraestructura clásica inhabilitada</dt>
<dd>El usuario ya no puede acceder a los recursos de la infraestructura clásica, pero puede iniciar una sesión en la consola y acceder a los recursos de la plataforma.</dd>
<dt>Solo VPN</dt>
<dd>El usuario no puede iniciar una sesión en la consola, pero tiene acceso a los dispositivos y subredes de VPN que asigne para la infraestructura clásica iniciando la sesión directamente en el dispositivo.</dd>
</dl>

Cuando se actualiza un usuario con el estado Solo VPN al estado Activo, el usuario debe conocer la contraseña para iniciar la sesión en la consola. En la mayoría de los casos, se trata de la contraseña del ID de SoftLayer, que es posible que deba restablecerse para que se pueda utilizar. En casos excepcionales en los que el usuario ya tiene un IBMid, debe iniciar la sesión con el IBMid y la contraseña.
{: note}

## Actualización del estado de un usuario
{: #update_user_status}

Para cambiar el estado de un usuario, siga los pasos siguientes:

1. En la barra de menús, pulse **Gestionar** &gt; **Acceso (IAM)** y seleccione **Usuarios**.
2. Seleccione un usuario de la lista.
3. En la página de detalles de usuario, seleccione una opción en el menú **Estado de usuario**.  
4. Pulse **Aplicar**.
