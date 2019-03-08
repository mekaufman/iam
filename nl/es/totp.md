---

copyright:

  years: 2018, 2019

lastupdated: "2019-01-30"

keywords: MFA, multifactor authentication, time-based one-time passcode, TOTP

subcollection: iam

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:tip: .tip}
{:note: .note}

# Habilitación de MFA de código de acceso de un solo uso para un usuario
{: #totp}

Como administrador con el acceso correcto, puede habilitar la opción de que se solicite a un usuario un código de acceso de un solo uso basado en tiempo (TOTP) al iniciar la sesión desde la página Usuario de la consola de {{site.data.keyword.Bluemix}}. Este tipo de autenticación de multifactores (MFA) solo es necesario para la cuenta en la que el valor está habilitado a diferencia de MFA basada en ID. Para obtener más información, consulte [Tipos de autenticación de multifactores.](/docs/iam?topic=iam-types#types).
{:shortdesc}

Si tiene alguno de los siguientes accesos, puede actualizar este valor para otros usuarios de la cuenta:

* Rol de editor o superior en el servicio de gestión de usuarios
* Es un antecesor en la jerarquía de la infraestructura clásica para el usuario y tiene asignado el permiso de la infraestructura clásica de gestión de usuarios

Para activar el valor de inicio de sesión para que se solicite MFA de TOTP a un usuario, siga estos pasos.

Para activar esta opción de MFA para un usuario, este debe [configurar TOTP](/docs/account?topic=account-MFA#MFA) primero desde la página Valores de inicio de sesión del perfil.
{: note}

1. En la barra de menús, pulse **Gestionar** &gt; **Acceso (IAM)** y seleccione **Usuarios**.
2. Seleccione un usuario de la lista.
3. En la página **Detalles de usuario** de la sección **Gestionar inicio de sesión del usuario**, active la opción **MFA de código de acceso de un solo uso basado en tiempo**.

Puede gestionar este valor usted mismo si tiene habilitado el valor de inicio de sesión gestionado por el usuario en la página de detalles de usuario.
{: tip}
