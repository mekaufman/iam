---

copyright:

  years: 2017, 2019

lastupdated: "2019-01-28"

keywords: classic infrastructure access, VPN subnet access, classic infrastructure permissions, device access

subcollection: iam

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:tip: .tip}
{:note: .note}
{:deprecated: .deprecated}

# Gestión del acceso a la infraestructura clásica
{: #mngclassicinfra}

Puede actualizar los permisos de los servicios de la infraestructura clásica o añadir acceso a dispositivos y a subred VPN para un usuario en cualquier momento. Para acceder a los permisos de la infraestructura clásica, vaya a **Gestionar** &gt; **Acceso (IAM)** y seleccione **Usuarios**. A continuación, seleccione el nombre del usuario para el que desea actualizar el acceso y pulse **Infraestructura clásica**.
{:shortdesc}

Debe tener asignado el permiso de la infraestructura clásica Gestionar usuarios y debe ser un antecesor del usuario dentro de la jerarquía de usuarios de la infraestructura clásica. Los propietarios de cuenta tienen acceso completo a la cuenta, de modo que no ven los permisos en la página. Los usuarios individuales no pueden editar sus propios permisos, y tampoco ven los permisos en la página.
{: note}

  1. Seleccione **Permisos** para actualizar los permisos del usuario. Puede seleccionar entre cuatro tipos de permisos: cuenta, dispositivos, red y servicios. Seleccione de forma individual los permisos de cada categoría, o utilice una opción de conjunto de permisos para asignar permisos de forma masiva.

    Los permisos de gestión de cuentas y de soporte que ha asignado previamente a los usuarios de la cuenta se migran de los permisos de la infraestructura clásica a los grupos de acceso de IAM migrados. Para obtener más información, consulte [Permisos migrados de la infraestructura clásica](/docs/iam?topic=iam-migrated_permissions).
    {: tip}

  2. Para otorgar a un usuario acceso a dispositivos, seleccione **Dispositivos** y asigne el acceso a dispositivos y a tipos de dispositivos específicos que necesite.

    El acceso a los dispositivos se asigna después de que se invite al usuario a la cuenta. Los permisos de dispositivos se aplican a los dispositivos específicos que se asignan para el usuario. Puede seleccionar dispositivos específicos en la lista o puede asignar acceso por tipo de dispositivo. Si asigna acceso por tipo de dispositivo, es posible que desee utilizar las opciones **Habilitar acceso futuro** para garantizar que cada vez que se añadan dispositivos de un tipo específico se asigne automáticamente al usuario acceso a dichos dispositivos.

  3. Para actualizar el acceso de un usuario a las subredes VPN, seleccione **Subredes VPN**.

    Utilice la opción **Asignar automáticamente** para definir el modo en que el usuario obtiene acceso a las subredes VPN en función de su acceso a dispositivos. Si esta opción está activada, se asigna automáticamente al usuario acceso a todas las subredes para los dispositivos a los que ya tienen acceso. Puede desactivar esta opción para seleccionar manualmente las subredes de la lista.
    {: tip}

    Para proporcionar acceso a las subredes VPN, al usuario ya debe tener asignado acceso a uno o varios dispositivos. Si el usuario no tiene acceso a ningún dispositivo, no hay ninguna subred que se pueda seleccionar. Puede definir el tipo de subredes VPN a las que tiene acceso el usuario utilizando la opción **Tipo de VPN**. Si selecciona **Ninguno**, no se puede asignar ningún acceso VPN.

    La opción PPTP está en desuso, de modo que, si la tiene y la deselecciona, deja de estar disponible.
    {: deprecated}
