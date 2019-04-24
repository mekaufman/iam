---

copyright:

  years: 2018, 2019

lastupdated: "2019-01-28"

keywords: specific IP addresses, IP addresses, restrict IP access, IP address access, allow IP access

subcollection: iam

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:tip: .tip}
{:note: .note}
{:important: .important}

# Cómo permitir direcciones IP específicas para un usuario
{: #ips}

De forma predeterminada, todas las direcciones IP se pueden utilizar para iniciar una sesión en la consola de {{site.data.keyword.cloud}} y acceder a las API de la infraestructura clásica. Puede especificar qué direcciones IP tienen acceso y solo se podrán utilizar las direcciones especificadas; las demás están restringidas.
{:shortdesc}

No puede acceder a las páginas de infraestructura clásica en [https://cloud.ibm.com](https://cloud.ibm.com){: new_window} ![Icono de enlace externo](../icons/launch-glyph.svg "Icono de enlace externo") si tiene direcciones IP restringidas. Debe ir a [https://control.softlayer.com](https://control.softlayer.com){: new_window} ![Icono de enlace externo](../icons/launch-glyph.svg "Icono de enlace externo").
{: important}

Si tiene asignado el acceso siguiente, puede actualizar las direcciones IP restringidas de otro usuario:

  * Una política de IAM con el rol de editor o superior en el servicio de gestión de usuarios.
  * Es un antecesor en la jerarquía de la infraestructura clásica para el usuario y tiene asignado el permiso de la infraestructura clásica de gestión de usuarios

Puede gestionar este valor usted mismo si tiene habilitado el valor de inicio de sesión gestionado por el usuario en la página de detalles de usuario.
{: tip}

Para restringir a un usuario a que utilice solo direcciones IP específicas, siga los pasos siguientes:

1. En la barra de menús, pulse **Gestionar** &gt; **Acceso (IAM)** y seleccione **Usuarios**.
2. Seleccione un usuario de la lista.
3. En la página de detalles de usuario, vaya a la sección **Restricciones de direcciones IP**.
4. Para la **Plataforma de nube**, escriba las direcciones IP. Las direcciones IP listadas son las únicas desde las cuales este usuario puede iniciar una sesión en {{site.data.keyword.Bluemix}}.
5. Para **Infraestructura clásica**, escriba las direcciones IP. Las direcciones IP listadas son las únicas desde las cuales el usuario puede llamar a una API de la infraestructura clásica.

  Para especificar en una dirección IP de la infraestructura clásica, el usuario ya debe haber creado una clave de API de la infraestructura clásica.
  {: note}
