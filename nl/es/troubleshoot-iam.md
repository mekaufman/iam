---

copyright:
  years: 2015, 2019
lastupdated: "2019-04-01"

---

{:tsSymptoms: .tsSymptoms}
{:tsCauses: .tsCauses}
{:tsResolve: .tsResolve}
{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:screen: .screen}
{:codeblock: .codeblock}
{:pre: .pre}
{:note:.deprecated}
{:troubleshoot: data-hd-content-type='troubleshoot'}

# Resolución de problemas de IAM
{: #troubleshoot_iam}

Entre los problemas generales con el uso de IAM se puede incluir la necesidad de acceder a un recurso o una cuenta para realizar una tarea o identificar el tipo adecuado de acceso para asignar a los usuarios de su cuenta para realizar tareas específicas. En muchos de los casos, puede solucionar estos problemas siguiendo unos sencillos pasos.
{:shortdesc}

## ¿Cómo sé qué acceso tengo asignado?
{: #troubleshoot-myaccess}
{: troubleshoot}

Si no tiene acceso para completar una tarea determinada, como crear una instancia de servicio y añadirla a un grupo de recursos o invitar a otros usuarios a la cuenta, debería comprobar qué acceso tiene asignado.

No estoy seguro de qué nivel de acceso tengo asignado para completar acciones en una cuenta de la cual soy miembro. 
{: tsSymptoms}
   
Es posible que no tenga asignado el acceso correcto. 
{: tsCauses}

Para comprobar a qué tiene acceso y el nivel de acceso, complete los siguientes pasos. Si necesita solicitar acceso, póngase en contacto con el propietario de la cuenta.

Vaya a **Gestionar** &gt; **Acceso (IAM)**, y seleccione su nombre en la página **Usuarios**. Luego, en función del acceso que busque, seleccione los distintos separadores:
{: tsResolve}

* Para determinar qué acceso tiene en los grupos de acceso que tiene asignados, seleccione **Grupos de acceso**.
* Para ver las políticas de acceso de IAM que tiene asignadas, seleccione **Políticas de acceso**.
* Para ver el acceso de Cloud Foundry para todas las organizaciones y espacios, seleccione **Acceso de Cloud Foundry**.


## ¿Cómo puedo obtener acceso para invitar a usuarios a la cuenta? 
{: #troubleshoot-invite}
{: troubleshoot}

Si no es el propietario de la cuenta y no tiene asignado el acceso correcto, no puede invitar a usuarios a una cuenta. 

No puedo invitar a usuarios a la cuenta.
{: tsSymptoms}
   
Es posible que no tenga asignado el acceso correcto. 
{: tsCauses}

Para invitar a usuarios y gestionar invitaciones pendientes, debe ser propietario de la cuenta, gestor de la organización, un usuario con una política de acceso de IAM con el rol de editor o superior sobre el servicio de gestión de cuentas o gestión de usuarios o bien debe tener permisos de la infraestructura para añadir usuarios.
{: tsResolve}


## ¿Cómo puedo ver los permisos de la infraestructura clásica para otros usuarios?
{: #troubleshoot-classicinfra}
{: troubleshoot}

Los propietarios de cuenta tienen acceso completo a la cuenta, de modo que no ven los permisos para ellos mismos. Los usuarios individuales no pueden editar sus propios permisos, por tanto, ven los permisos en su página de la infraestructura clásica pero no pueden editarlos. Debe tener acceso específico para ver y editar permisos para otro usuario en la cuenta.

Le aparece un mensaje que indica que no puede ver los permisos de la infraestructura clásica de otro usuario.
{: tsSymptoms}
   
Es posible que no tenga asignado el acceso correcto.
{: tsCauses}

Deberá solicitar al propietario de la cuenta que le asigne el permiso de la infraestructura clásica **Gestionar usuarios**, pero también debe ser un antecesor del usuario dentro de la jerarquía de usuarios de la infraestructura clásica para ver y gestionar los permisos de otro usuario.
{: tsResolve}
