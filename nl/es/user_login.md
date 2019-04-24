---

copyright:

  years: 2018, 2019

lastupdated: "2019-01-28"

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:tip: .tip}
{:important: .important}

# Gestión de los valores de inicio de sesión de un usuario 
{: #loginsettings}

Un propietario de cuenta, o un usuario que tenga el acceso correcto, puede gestionar los valores de inicio de sesión de un usuario; por ejemplo, puede solicitar opciones de autenticación externa, habilitar un código de acceso de un solo uso que se utilizará durante el inicio de sesión, habilitar el uso de preguntas de seguridad al iniciar sesión y establecer un periodo de tiempo de caducidad de la contraseña.
{:shortdesc}

Siga los pasos siguientes para gestionar los valores de inicio de sesión para un usuario específico:

1. En la barra de menús, pulse **Gestionar** &gt; **Acceso (IAM)** y seleccione **Usuarios**. 
2. Seleccione un usuario de la lista y pulse **Detalles de usuario**. 
3. Desde la sección **Gestionar inicio de sesión de usuario**, puede activar o desactivar las opciones siguientes para el usuario seleccionado: 
    
    * MFA de código de acceso de un solo uso basado en tiempo: active esta opción para que se solicite al usuario un código de acceso de un solo uso al iniciar la sesión. El usuario debe configurar su MFA TOTP desde la página de valores de inicio de sesión. Para obtener más información, consulte [Habilitación de MFA de código de acceso de un solo uso para un usuario](/docs/iam?topic=iam-totp#totp).
    
    * Solicitar autenticación externa: seleccione esta opción para adquirir autenticación de Symantec o por teléfono con un coste mensual. Solo se puede solicitar y utilizar una opción cada vez. Para obtener más información, consulte [Solicitud de MFA de autenticación externa para un usuario](/docs/iam?topic=iam-external#external).

        * Autenticación por teléfono: el usuario puede utilizar esta opción usando la configuración que ha configurado en la página Detalles de usuario después de que el propietario de la cuenta la solicite. 
        * Autenticación de Symantec: el usuario puede utilizar esta opción después de que el propietario de la cuenta la solicite. Para que un administrador solicite esta opción, el usuario debe proporcionar primero su ID de credencial.

    * Preguntas de seguridad de MFA durante el inicio de sesión: active eta opción para que se solicite al usuario las preguntas y respuestas de seguridad que ha configurado en la página Valores de inicio de sesión. No puede activar esta opción a menos que el usuario ya haya configurado sus preguntas de seguridad. Para obtener más información, consulte [Habilitación de preguntas de seguridad de MFA para un usuario](/docs/iam?topic=iam-questions#questions).

    * Inicio de sesión gestionado por el usuario: active esta opción para permitir que el usuario defina la caducidad de una contraseña, active preguntas de seguridad para el inicio de sesión y especifique las direcciones IP permitidas para las API de inicio de sesión de {{site.data.keyword.cloud_notm}} y de la infraestructura clásica. 

    * Caducidad de contraseña: establezca una caducidad seleccionando una opción de la lista. Esta opción solo está disponible para los usuarios con un ID de SoftLayer. Si el usuario puede gestionar sus propios valores de inicio de sesión, puede definir esta caducidad en la página de valores de inicio de sesión. Solo los usuarios con los permisos siguientes pueden definir una caducidad de contraseña para un usuario:
        
        * Cualquier usuario que tenga asignada una política de IAM con el rol de editor o superior en el servicio de gestión de usuarios.
        * Cualquier usuario que tenga habilitado el inicio de sesión gestionado por el usuario en la página de detalles del usuario por su administrador.
        * Cualquier antecesor en la jerarquía de la infraestructura clásica para el usuario que tenga asignado el permiso de la infraestructura clásica de gestión de usuarios.

Solo se debe habilitar una opción de MFA a la vez. Si se necesita MFA de IBMid para cualquier cuenta de la que el usuario es miembro, esta sustituye cualquier otra MFA que esté habilitada y no se solicita al usuario ningún otro tipo de MFA.
{: important}



