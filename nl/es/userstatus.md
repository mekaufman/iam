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


# Estado de usuario
{: #user_status}

Cuando se invita a un usuario a la cuenta, en función del tipo de usuario y de su estado de aceptación de la invitación, se le asigna un estado que se muestra en la página **Detalles de usuario** para un usuario concreto. 
{:shortdesc}

| Estado usuario | Descripción |
|:-----------|:------------|
| Activo | El usuario ha aceptado la invitación y tiene asignado el acceso para trabajar dentro de la cuenta. | 
| Infraestructura clásica inhabilitada | El propietario de la cuenta o un usuario con permisos suficientes puede establecer otro usuario como inhabilitado de modo que el usuario ya no pueda acceder a los recursos de la infraestructura clásica. El usuario puede seguir iniciando sesión en la consola y acceder a los recursos de la plataforma. |
| Solo VPN | Un usuario que se crea en la cuenta, pero que está restringido a solo acceso VPN solo para dispositivos. Este tipo de usuario no tiene acceso para iniciar una sesión en la consola.| 
| Procesando | Un estado poco frecuente en el que el usuario se añade a una invitación, pero la invitación no se ha enviado y el sistema ha creado la primera instancia del usuario. |
| Pendiente | Un estado en el que se ha invitado a un usuario pero no ha aceptado la invitación o se ha unido a la cuenta creando una cuenta de {{site.data.keyword.Bluemix_notm}}. |
{: caption="Tabla 1. Estado de usuario" caption-side="top"} 

Para obtener información sobre cómo cambiar el estado de un usuario, consulte [Actualización del estado de un usuario](/docs/iam?topic=iam-status#status).

