---

copyright:

  years: 2017, 2019

lastupdated: "2019-01-30"

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:tip: .tip}
{:note: .note}


# Concesión de acceso entre los servicios
{: #serviceauth}

Muchas de las prestaciones del sistema {{site.data.keyword.Bluemix_notm}} Identity and Access Management (IAM) se centran en gestionar y aplicar el acceso a recursos de {{site.data.keyword.Bluemix_notm}} por parte de los usuarios y sus aplicaciones. Sin embargo, existen otros casos en los que puede que tenga que proporcionar un servicio con acceso a recursos de un usuario en otro servicio. Todos los usuarios de la cuenta pueden crear una autorización, pero sólo un usuario con el rol de administrador puede suprimir una autorización. Puede configurar y ver las autorizaciones que se han otorgado en su cuenta en la página **Autorizaciones**. 
{:shortdesc}

## Crear una autorización
{: #create-auth}

Solo puede otorgar el nivel de acceso que tenga como un usuario del servicio de destino. Por ejemplo, si solo tiene acceso de visor en el servicio al que se va a acceder, solo puede asignar el rol de visor para la autorización.

1. En la barra de menús, pulse **Gestionar** &gt; **Acceso (IAM)** y seleccione **Autorizaciones**. 
2. Pulse **Crear**.
3. Seleccione un servicio de origen y de destino para la autorización. Al servicio de origen se le da acceso al servicio de destino seleccionado.
4. Seleccione un rol para asignar acceso al servicio de origen cuando acceda al servicio de destino.
5. Pulse **Autorizar**.

Solo están disponibles como opciones los servicios que permiten otorgar este tipo de acceso.
{: note}

## Eliminar una autorización
{: #remove-auth}

1. En la barra de menús, pulse **Gestionar** &gt; **Acceso (IAM)** y seleccione **Autorizaciones**. 
2. Identifique la fila de la autorización que desea eliminar de la cuenta.
3. En el menú **Acciones** ![Icono Lista de acciones](../icons/action-menu-icon.svg), seleccione **Eliminar**.
5. Seleccione **Eliminar**.
