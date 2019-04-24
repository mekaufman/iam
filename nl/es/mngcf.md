---

copyright:

  years: 2017, 2019

lastupdated: "2019-01-28"

keywords: Cloud Foundry access, assign access, add user to organization, Cloud Foundry roles

subcollection: iam

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}

# Gestión del acceso de Cloud Foundry
{: #mngcf}

Para gestionar el acceso a espacios y organizaciones de la cuenta, debe ser el propietario de la cuenta, un gestor de organización o un gestor de espacio.
{:shortdesc}

## Actualización del acceso de Cloud Foundry
{: #update_cf_access}

1. En la barra de menús, pulse **Gestionar** &gt; **Acceso (IAM)** y seleccione **Usuarios**.
2. En la fila correspondiente al usuario al que desea asignar acceso, seleccione el menú **Acciones** ![Icono Lista de acciones](../icons/action-menu-icon.svg) y pulse **Asignar acceso**.
3. Seleccione **Asignar utilizando Cloud Foundry**.
4. Expanda la fila de la organización a la que está asignado el usuario para ver el acceso del usuario a los espacios y sus roles en estos espacios.
5. En el menú **Acciones** ![Icono Lista de acciones](../icons/action-menu-icon.svg) de la sección Cloud Foundry, puede:

  * Eliminar el usuario de la organización
  * Editar el rol de la organización
  * Editar el rol de espacio

## Adición de un usuario a una organización
{: #add_to_org}

Si es el gestor de una organización de la que el usuario aún no es miembro, puede asignar al usuario a esa organización.

1. En la barra de menús, pulse **Gestionar** &gt; **Acceso (IAM)** y seleccione **Usuarios**.
2. En la fila correspondiente al usuario al que desea asignar acceso, seleccione el menú **Acciones** ![Icono Lista de acciones](../icons/action-menu-icon.svg) y pulse **Asignar acceso**.
3. Seleccione **Asignar utilizando Cloud Foundry**.
4. Seleccione **Asignar organización**.
5. Asigne el acceso de usuario:
   * Elija una organización en la que añadir al usuario:
   * Asigne un rol de organización
   * Elija una región
   * Elija un espacio
   * Asigne un rol de espacio
7. Pulse **Asignar**.

## Revisión de su acceso asignado
{: #review_my_access}

Si necesita revisar su acceso asignado en una cuenta a la que ha sido añadido, complete los siguientes pasos:

1. En la barra de menús, pulse **Gestionar** &gt; **Acceso (IAM)** y seleccione **Usuarios**.
2. Seleccione su nombre.
3. Pulse **Acceso de Cloud Foundry**.
3. Expanda la fila de la organización y revise los roles asignados.

Si necesita acceso adicional, debe ponerse en contacto con el gestor de la organización o el propietario de la cuenta para actualizar el rol de Cloud Foundry que tiene asignado.
