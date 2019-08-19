---

copyright:

  years: 2018, 2019

lastupdated: "2019-08-09"

keywords: remove user, delete user

subcollection: iam

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:tip: .tip}

# Eliminar usuarios de una cuenta
{: #remove}

Cuando elimina un usuario de una cuenta, el usuario deja de poder iniciar una sesión en la consola, cambiar a su cuenta si sigue perteneciendo a otra cuenta y acceder a los recursos de la cuenta. Al eliminar un usuario de una cuenta, no se suprime el IBMid de dicho usuario.
{:shortdesc}

Solo los propietarios de la cuenta o los usuarios con el siguiente acceso pueden eliminar usuarios de una cuenta:

* Una política de IAM para el servicio de gestión de cuenta de gestión de usuarios con el rol de administrador asignado y debe ser el gestor de organización de Cloud Foundry si el usuario pertenece a una organización de Cloud Foundry.
* Si tiene la infraestructura clásica en su cuenta, un usuario debe tener una política de IAM para el servicio de gestión de cuentas de gestión de usuarios con el rol de administrador asignado, debe ser el gestor de organización de Cloud Foundry si el usuario pertenece a una organización de Cloud Foundry y debe ser un antecesor del usuario en la jerarquía de usuarios de la infraestructura clásica con el permiso de gestión de usuarios de infraestructura clásica asignado.

Para eliminar un usuario de una cuenta, realice estos pasos:

1. En la barra de menús, pulse **Gestionar** &gt; **Acceso (IAM)** y seleccione **Usuarios**.
2. En la fila del usuario que desea eliminar, seleccione **Eliminar usuario** en el menú **Acciones** ![Icono Lista de acciones](../icons/action-menu-icon.svg).

Los recursos que ha creado el usuario permanecen en la cuenta. No obstante, el usuario ya no tiene acceso a trabajar con esos recursos, por lo que el propietario de la cuenta o un administrador de ese servicio o instancia de servicio puede asignar a otros usuarios para trabajar con esos recursos o bien suprimirlos de la cuenta.

Si recibe un mensaje de error indicando que un usuario de infraestructura clásica no se puede eliminar, asegúrese de los descendientes de dicho usuario en la jerarquía de usuarios [tengan un nuevo padre asignado](/docs/iam?topic=iam-update-parent), [estén inhabilitados en la cuenta](/docs/iam?topic=iam-status) o se hayan suprimido y vuelva a intentarlo.
{: tip}
