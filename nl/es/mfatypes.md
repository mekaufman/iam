---

copyright:

  years: 2018,2019
lastupdated: "2019-01-02"

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:tip: .tip}
{:note: .note}

# Tipos de autenticación de multifactores
{: #types}

La autenticación de multifactores (MFA) añade una capa adicional de seguridad a su cuenta al exigir a todos los usuarios que se autentiquen utilizando un método de autenticación adicional, además de un ID y una contraseña. También se conoce como autenticación de dos factores (2FA).
{:shortdesc}

Se pueden habilitar los dos tipos siguientes de opciones de MFA para su cuenta:

<dl>
<dt>MFA basada en ID</dt>
<dd>Opción que habilita el propietario de una cuenta en una de las cuentas de las que es miembro. Este tipo de MFA está asociado con el IBMid y le autentica en todas las cuentas a las que es miembro, por lo que solo tiene que autenticarse una vez.</dd>
<dt>Opciones basadas en cuenta</dt>
<dd>Opciones como preguntas de seguridad, uso de un código de acceso de un solo uso y opciones de autenticación externa, como la autenticación Symantec y por teléfono. Estos tipos de MFA son específicos de la cuenta, lo que significa que, si tiene un tipo distinto configurado para cada cuenta a la que pertenece, debe autenticarse de distintas formas cada vez que cambie de cuenta. Estas opciones antiguas de MFA solo están disponibles con cuentas anteriores de la infraestructura clásica.</dd>
</dl>

MFA de IBMid satisface el requisito de autenticación, de modo que no se le solicitan otros tipos de MFA aunque estén habilitados. Por lo tanto, si alguno de los propietarios de una cuenta en la que es miembro activa esta opción, este es el único tipo de MFA que se le solicitará cuando inicie una sesión. Si es un usuario nuevo, utilice la opción MFA de IBMid basada en ID para asegurarse de que su inicio de sesión sea fácil y seguro.
{: tip}

## Opción MFA basada en ID
{: #id-based}

MFA de IBMid para una cuenta requiere un código de acceso de un solo uso basado en el tiempo, además de un IBMid estándar y una contraseña durante el inicio de sesión. El propietario de la cuenta habilita este tipo de MFA a nivel de cuenta. Cuando esta característica está habilitada, debe utilizar el estándar de seguridad adicional al iniciar una sesión, y también deben hacerlo todos los usuarios que se añadan a su cuenta. Este tipo de MFA se aplica a todos los recursos de la cuenta. Puede activarlo o desactivarlo desde la página **Gestionar** > **Acceso (IAM)** > **Valores** en la consola de {{site.data.keyword.Bluemix}} solo si es el propietario de la cuenta.

Una de las ventajas de MFA de IBMid es que es gratuita y está vinculada a su ID, en lugar de estarlo solo a la cuenta específica en la que se encuentra. Si pertenece a varias cuentas, solo se tiene que autenticar una vez cuando inicie una sesión en la consola. Para obtener más información sobre MFA de IBMid, sobre las consideraciones que se deben revisar antes de requerir MFA de IBMid para su cuenta y sobre cómo configurar MFA de IBMid para usted mismo, consulte [Requerimiento de MFA para usuarios de su cuenta](/docs/iam/mfa.html#setting-up-ibmid-mfa).

## Opciones de MFA basada en cuenta
{: #account-based}

Un administrador de la cuenta debe habilitar cualquiera de las siguientes opciones de MFA para que un usuario las pueda configurar y utilizar en la cuenta. Este tipo de MFA está vinculado a la cuenta actual de un usuario. Si un administrador habilita una opción de MFA diferente para cada cuenta de la que un usuario es miembro, el usuario debe autenticarse de una forma distinta cada vez que cambie de cuenta. 

Si un propietario de cuenta requiere MFA de IBMid para todos los usuarios de la cuenta, este método MFA de IBMid sustituye cualquier otra opción de MFA que esté habilitada y establecida en la cuenta de un usuario. Por lo tanto, aunque un usuario tenga otras opciones de MFA, como por ejemplo la siguiente configuración, no se le solicitarán durante el inicio de sesión.

Las siguientes opciones antiguas de MFA solo están disponibles con cuentas anteriores de la infraestructura clásica.

<dl>
<dt>Autenticación de código de acceso de un solo uso basado en tiempo (TOTP)</dt>
<dd>TOTP se puede configurar mediante una app de autenticación. Un propietario de cuenta o un administrador puede habilitar este valor para un usuario en la página de detalles de usuario solo si el usuario ha configurado la autenticación en la página de valores de inicio de sesión del perfil. Si este valor está habilitado para un usuario, se le solicita el código de acceso durante el inicio de sesión. Los usuarios que tienen acceso para gestionar sus propios valores de inicio de sesión porque tienen activado el valor de inicio de sesión gestionado por el usuario en la página de detalles de usuario pueden activarlo y desactivarlo.</dd>
<dt>Preguntas de seguridad</dt>
<dd>Los usuarios pueden configurar respuestas a las preguntas de seguridad que están disponibles en la página de valores de inicio de sesión del perfil. El usuario debe configurar las preguntas y respuestas de seguridad para que un propietario de la cuenta o administrador pueda habilitar este valor en la página de detalles de usuario. Los usuarios que tienen acceso para gestionar sus propios valores de inicio de sesión porque tienen activado el valor de inicio de sesión gestionado por el usuario en la página de detalles de usuario pueden activarlo y desactivarlo. </dd>
<dt>Autenticación externa</dt>
<dd>Hay dos opciones de autenticación externa de terceros que se pueden solicitar con un coste mensual: autenticación de Symantec y autenticación por teléfono. Un propietario de cuenta o administrador debe solicitar estas opciones para un usuario y habilitarlas para que se puedan utilizar desde la página de detalles de usuario para el usuario. En el caso de Symantec, el administrador debe trabajar con el usuario para obtener el ID de credencial de dicho usuario para realizar el pedido. Para configurar la autenticación por teléfono, el administrador debe solicitarla y luego el usuario debe configurarla en su página de detalles de usuario para que el administrador pueda habilitarla para su uso. Los usuarios que tienen acceso para gestionar sus propios valores de inicio de sesión porque tienen activado el valor de inicio de sesión gestionado por el usuario en la página de detalles de usuario pueden activarlo y desactivarlo.</dd>
</dl>

Para obtener más información sobre cómo configurar las opciones de MFA, consulte [Configuración de la seguridad de inicio de sesión](/docs/account/login_settings.html#login-settings). Si es un propietario de cuenta o administrador que gestiona los valores de inicio de sesión de otros usuarios o si tiene capacidad para gestionar sus propios valores de inicio de sesión, consulte [Gestión de los valores de inicio de sesión de un usuario](/docs/iam/user_login.html#loginsettings).

