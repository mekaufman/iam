---

copyright:

  years: 2018, 2019

lastupdated: "2019-01-30"

keywords: security questions, MFA, multifactor authentication, login security

subcollection: iam

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:tip: .tip}
{:note: .note}

# Habilitación de preguntas de seguridad de MFA para un usuario
{: #questions}

Como administrador con el acceso correcto, puede habilitar la opción de que se solicite a un usuario preguntas y respuestas de seguridad al iniciar la sesión. Este tipo de autenticación de multifactores (MFA) solo es necesario para la cuenta en la que el valor está habilitado. Este tipo de autenticación de multifactores (MFA) solo es necesario para la cuenta en la que el valor está habilitado a diferencia de MFA basada en ID. Para obtener más información, consulte [Tipos de autenticación de multifactores.](/docs/iam?topic=iam-types#types).
{:shortdesc}

Si tiene alguno de los siguientes accesos, puede actualizar este valor para otros usuarios de la cuenta:

* Rol de editor o superior en el servicio de gestión de usuarios
* Es un antecesor en la jerarquía de la infraestructura clásica para el usuario y tiene asignado el permiso de la infraestructura clásica de gestión de usuarios


Para activar esta opción de MFA para un usuario, este debe [configurar preguntas de seguridad](/docs/account?topic=account-security-questions#security-questions) y respuestas desde la página Valores de inicio de sesión del perfil.
{: note}

1. En la barra de menús, pulse **Gestionar** &gt; **Acceso (IAM)** y seleccione **Usuarios**.
2. Seleccione un usuario de la lista.
3. En la página **Detalles de usuario** de la sección **Gestionar inicio de sesión del usuario**, active la opción **Requerir preguntas de seguridad de MFA durante el inicio de sesión**.

Puede gestionar este valor usted mismo si tiene habilitado el valor de inicio de sesión gestionado por el usuario en la página de detalles de usuario.
{: tip}
