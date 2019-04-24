---

copyright:

  years: 2018, 2019
lastupdated: "2019-03-05"

keywords: MFA, multifactor authentication, IBMid MFA, two-factor authentication, account MFA, time-based one-time passcode, TOTP

subcollection: iam

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:tip: .tip}
{:note: .note}

# Requerimiento de MFA para usuarios de la cuenta
{: #enablemfa}

Como propietario de una cuenta de {{site.data.keyword.Bluemix}} o administrador del servicio de facturación, puede decidir si quiere exigir la autenticación de multifactores (MFA) para cada usuario de la cuenta. Todos los usuarios con un IBMid utilizan un método de MFA de código de acceso de un solo uso basado en tiempo (TOTP), y cualquier usuario con otro tipo de ID se debe habilitar para que pueda utilizar TOTP, preguntas de seguridad o un método de autenticación externa independiente.  
{:shortdesc}

## Antes de empezar
{: #considerations}

Revise las siguientes consideraciones antes de habilitar MFA de IBMid para su cuenta para asegurarse de que sabe cómo afecta a todos los usuarios de su cuenta:

* Cuando habilite la MFA en su cuenta, los usuarios deben completar el proceso de MFA la próxima vez que inicien una sesión.
* Las claves de API para los usuarios y los ID de servicio seguirán funcionando cuando la MFA esté habilitada.
* Si necesita utilizar una CLI CF nativa o un inicio de sesión de IU en Cloud Foundry, debe utilizar las claves de API o el inicio de sesión único (SSO) cuando la MFA esté habilitada en la cuenta.
* MFA para su cuenta se aplica al inicio de sesión de un usuario, pero no se aplica a las llamadas de API. Si un usuario tiene permiso para realizar llamadas de API a los recursos de su cuenta, el usuario puede hacerlo sin completar la MFA. Si el usuario pertenece a otras cuentas, el usuario puede realizar llamadas de API a los recursos de su cuenta utilizando una clave de API de una cuenta que no requiera MFA.
* Si es un usuario federado, la MFA no se admite.
* Si necesita MFA para su cuenta y tiene usuarios en su cuenta que no tienen un IBMid, debe habilitar una de las otras opciones de MFA para dicho usuario desde la página de detalles de usuario en la consola de {{site.data.keyword.Bluemix_notm}}. Para obtener más información, consulte [Tipos de autenticación de multifactores.](/docs/iam?topic=iam-types#types).
* Planifique una estrategia de soporte y comunicación para los usuarios de su cuenta:
  * Elija la fecha y la hora en habilitar la MFA que produzca el menor impacto en su empresa.
  * Cuando haya habilitado la MFA, proporcione a los usuarios de su cuenta información sobre cómo [realizar la configuración](/docs/iam?topic=iam-enablemfa#setupapp).

Cuando se habilita el valor de cuenta de autenticación de multifactores, se solicita a todos los usuarios de IBMid de la cuenta la autenticación de MFA de IBMid al iniciar sesión. Si tiene otros métodos de MFA configurados para cualquier usuario de IBMid en su cuenta, ya no se le solicita dichos métodos MFA.
{: tip}

## Habilitación de MFA para todos los usuarios de su cuenta
{: #enabling}

Para habilitar la MFA, debe ser el propietario de la cuenta o un administrador del servicio de gestión de la cuenta de facturación. La habilitación de la MFA no afecta a los usuarios que ya han iniciado sesión, ya que el cumplimiento de la MFA de la cuenta solo tiene vigencia en los inicios de sesión nuevos. Asegúrese de comunicar a los usuarios de su cuenta que se ha habilitado MFA y de describir el impacto sobre los usuarios en el siguiente inicio de sesión.

1. En la barra de menús, pulse **Gestionar** &gt; **Acceso (IAM)** y seleccione **Valores**.
2. Seleccione **Actualizar** para el valor de Inicio de sesión de cuenta.
3. Seleccione **Ninguno** o **Solo usuarios no federados** en función de qué tipo de autenticación desee que se requiera.
4. Marque el recuadro de selección para confirmar que entiende el impacto de requerir MFA para los usuarios de la cuenta, si selecciona la opción de solo usuarios no federados.
5. Pulse **Guardar**.

## Configuración de su TOTP
{: #setupapp}

Después de habilitar la MFA para su cuenta, debe configurar el código de acceso de un solo uso con una app de autenticador la próxima vez que inicie sesión. Todos los usuarios de su cuenta deben configurar también el código de acceso de un solo uso la próxima vez que inicien sesión.

Complete los pasos siguientes para configurar por primera vez el código de acceso de un solo uso con una app de autenticador:

1. Inicie sesión con su IBMid y contraseña.

  Se puede tardar hasta 5 minutos en iniciar sesión de nuevo con la MFA.
  {: note}

2. Seleccione **Verificar** en la pantalla **Es necesaria la verificación** para configurar la MFA con una app de autenticador.
3. Seleccione **Configurar la app de autenticador** para obtener un código de acceso de un solo uso en su correo electrónico y continuar configurando la app de autenticador.
4. Seleccione **Verificar**.
5. Explore el código de barras con su app o pulse **¿No puede explorar el código de barras?** para especificar una clave proporcionada.
6. Pulse **Continuar** para introducir el código.
7. Especifique el código y seleccione **Verificar**.

Si encuentra un mensaje de error que indica que ya ha configurado la autenticación, pero su código de verificación no funciona o no tiene un código de verificación que especificar, póngase en contacto con el [Centro de atención al cliente](https://www.ibm.com/ibmid/myibm/help/us/helpdesk.html){: new_window} ![Icono de enlace externo](../icons/launch-glyph.svg "Icono de enlace externo") para restablecer la inscripción de MFA.
{: note}
{: #mfahelp}

## Inhabilitación de MFA necesaria para todos los usuarios de su cuenta
{: #disablemfa}

Para inhabilitar la MFA, debe ser el propietario de la cuenta o un administrador del servicio de facturación de gestión de la cuenta. La inhabilitación de la MFA no afecta a los usuarios que ya han iniciado sesión. La acción será efectiva en todos los inicios de sesión nuevos.

1. En la barra de menús, pulse **Gestionar** &gt; **Acceso (IAM)** y seleccione **Valores**.
2. Seleccione **Editar** para el valor de Inicio de sesión de cuenta.
3. Seleccione **Ninguno**.
4. Pulse **Guardar**.

