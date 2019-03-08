---

copyright:

  years: 2018, 2019

lastupdated: "2019-01-30"

keywords: MFA, multifactor authentication, external authentication, order authentication, Symantec, phone-based authentication, cancel authentication order

subcollection: iam

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:tip: .tip}

# Solicitud de MFA de autenticación externa para un usuario
{: #external}

Como administrador con el acceso correcto, puede solicitar autenticación externa y habilitar la opción de autenticación de multifactores (MFA) para el inicio de sesión de un usuario. Se le facturará una tarifa mensual por las opciones de autenticación externa. Este tipo de autenticación de multifactores (MFA) solo es necesario para la cuenta en la que el valor está habilitado a diferencia de MFA basada en ID. Para obtener más información, consulte [Tipos de autenticación de multifactores.](/docs/iam?topic=iam-types#types).
{:shortdesc}

## Solicitud de autenticación externa
{: #ordering}

Si tiene el acceso siguiente, puede solicitar autenticación externa para un usuario:

* Rol de editor o superior en el servicio de gestión de usuarios
* Es un antecesor en la jerarquía de la infraestructura clásica para el usuario y tiene asignado el permiso de la infraestructura clásica de gestión de usuarios

Para solicitar la autenticación externa, siga los pasos siguientes:

1. En la barra de menús, pulse **Gestionar** &gt; **Acceso (IAM)** y seleccione **Usuarios**.
2. Seleccione un usuario de la lista.
3. En la página **Detalles de usuario**, seleccione **Pedir autenticación externa** en la sección Gestionar inicio de sesión de usuario.
4. Seleccione **Protección de identidad Symantec** o **Protección de identidad por teléfono**.
    * Para la autenticación de Symantec, el usuario debe descargar la aplicación [VIP de Symantec](https://vip.symantec.com/){: new_window} ![Icono de enlace externo](../icons/launch-glyph.svg) y obtener un ID de credencial para continuar con el proceso de solicitud.
    * Para la autenticación por teléfono, puede continuar con la solicitud, pero el usuario debe [configurar su configuración](/docs/account?topic=account-third-party-MFA#third-party-MFA) para que pueda habilitar la opción.
5. En función de su selección, siga las indicaciones para revisar el precio y los términos antes de realizar el pedido.
6. Pulse **Pedido** para finalizar la selección.

Después de solicitar la autenticación de Symantec, puede activar la opción para el usuario desde la página de detalles de usuario. Y, después de que se solicite la autenticación por teléfono y de que el usuario la configure, puede activar la opción para el usuario desde la página de detalles de usuario.

## Inhabilitación de las opciones de autenticación externa
{: #disable}

Puede inhabilitar MFA de Symantec o por teléfono para un usuario en cualquier momento.

1. En la barra de menús, pulse **Gestionar** &gt; **Acceso (IAM)** y seleccione **Usuarios**.
2. Seleccione un usuario de la lista.
3. Desde la página **Detalles de usuario**, desactive la opción **Autenticación de Symantec** o **Autenticación por teléfono**.

## Cancelación de las opciones de autenticación externa
{: #cancel}

Puede cancelar su pedido de autenticación externa siempre que lo desee, si tiene el acceso correcto. Puede cancelar de inmediato sin reembolso o puede cancelar pasado un año desde que la solicitó.

Para cancelar un pedido de autenticación externa, debe ser el propietario de la cuenta o debe tener todo el acceso siguiente:

* Permiso de la infraestructura clásica para gestionar usuarios
* Permiso de la infraestructura clásica para cancelar servicios
* Administrador del servicio de gestión de cuentas del centro de soporte o permisos migrados de la infraestructura clásica para ver, editar y añadir incidencias que no están disponibles en los [grupos de acceso de permisos migrados](/docs/iam?topic=iam-predefined#predefined).

Para cancelar el pedido de autenticación externa, siga los pasos siguientes:

1. En la barra de menús, pulse **Gestionar** &gt; **Acceso (IAM)** y seleccione Usuarios.
2. Seleccione un usuario de la lista.
3. En la página **Detalles de usuario**, pulse **Suprimir** ![Icono Suprimir](../icons/icon_trash.svg) para la fila **Autenticación de Symantec** o **Autenticación por teléfono** según la opción que haya solicitado.
4. Seleccione cuándo desea eliminarla.
5. Pulse **Eliminar**.
