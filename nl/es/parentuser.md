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

# Actualización del usuario padre de un usuario
{: #update-parent}

Si tiene el acceso correcto, puede actualizar el padre de un usuario. La actualización del usuario padre afecta a la forma en que un usuario ve a otros usuarios en la cuenta cuando el valor de visibilidad de la lista de usuarios está establecido en restringido. Los usuarios solo ven a otros usuarios de los que son padres y a cualquier otro usuario invitado por dichos descendientes del usuario padre.
{:shortdesc}

Consulte [valor de visibilidad de lista de usuarios](/docs/iam?topic=iam-userlistview#userlistview) para obtener más información sobre el valor. 

Si tiene el acceso siguiente, puede actualizar el padre de otro usuario:

* Una política de IAM con el rol de editor o superior en el servicio de gestión de usuarios.
* Es un antecesor en la jerarquía de la infraestructura clásica para el usuario y tiene asignado el permiso de la infraestructura clásica de gestión de usuarios


Para actualizar el padre de un usuario, siga los pasos siguientes:

1. En la barra de menús, pulse **Gestionar** &gt; **Acceso (IAM)** y seleccione **Usuarios**.  
2. Seleccione un nombre de usuario de la lista.
3. En la página de detalles de usuario, seleccione un nuevo usuario padre en el menú **Padre**.
4. Pulse **Aplicar**.
