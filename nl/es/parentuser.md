---

copyright:

  years: 2018, 2019

lastupdated: "2019-01-28"

keywords: parent user, change parent user, classic infrastructure hierarchy

subcollection: iam

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:tip: .tip}

# Actualización del usuario padre de un usuario
{: #update-parent}

Si tiene el acceso correcto, puede actualizar el padre de un usuario. La actualización del usuario padre afecta a la forma en que un usuario ve a otros usuarios en la cuenta cuando el valor de visibilidad de la lista de usuarios está establecido en restringido. Los usuarios solo ven otros usuarios de los que son padres y cualquier otro usuario que esté invitado por dichos descendientes del usuario padre.
{:shortdesc}

Para obtener más información sobre el valor, consulte [Configuración del acceso de vista del usuario](/docs/iam?topic=iam-userlistview#userlistview).

Si tiene el acceso siguiente, puede actualizar el padre de otro usuario:

* Una política de IAM con el rol de editor o superior en el servicio de gestión de usuarios.
* Es un antecesor en la jerarquía de la infraestructura clásica para el usuario y tiene asignado el permiso de la infraestructura clásica de gestión de usuarios


Para actualizar el padre de un usuario, siga los pasos siguientes:

1. En la barra de menús, pulse **Gestionar** &gt; **Acceso (IAM)** y seleccione **Usuarios**.  
2. Seleccione un nombre de usuario de la lista.
3. En la página de detalles de usuario, seleccione un nuevo usuario padre en el menú **Padre**.
4. Pulse **Aplicar**.
