---

copyright:

  years: 2019

lastupdated: "2019-03-25"

keywords: public access, anonymous access

subcollection: iam

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:tip: .tip}
{:note: .note}

# Habilitación del acceso público a recursos
{: #public}

El acceso público a recursos permite que todos los usuarios y los ID de servicio puedan acceder a un recurso específico de su cuenta. Esto significa que un usuario o ID de servicio no necesita autenticarse en {{site.data.keyword.Bluemix}} para acceder a información de, por ejemplo, un grupo de {{site.data.keyword.cos_full_notm}}. Solo determinados servicios dan soporte a la posibilidad de proporcionar acceso público a tipos de recurso específicos para el servicio. Por lo tanto, está limitado a crear políticas solo para los servicios que dan soporte a esta característica.
{:shortdesc}

Para habilitar el acceso público a recursos, debe utilizar el grupo de acceso **Acceso público** que se incluye automáticamente en su cuenta. Este grupo de acceso incluye todos los usuarios y los ID de servicio de forma predeterminada. No puede suprimir el grupo ni cambiar la pertenencia al grupo, pero puede añadir, editar y suprimir políticas de acceso para el grupo.

## Creación de una política para el grupo de acceso público
{: #public_policy}

Siga los siguientes pasos para asignar una política a su grupo de acceso público. La siguiente tarea utiliza el servicio Cloud Object Storage como ejemplo para asignar acceso público a un grupo denominado `mybucket123`.

1. En la barra de menús, pulse **Gestionar** &gt; **Acceso (IAM)** y seleccione **Grupos de acceso**.
2. Seleccione el grupo **Acceso público**.
3. Pulse **Asignar acceso**.
4. Seleccione **Cloud Object Storage** en la lista de servicios.
5. Escriba `grupo` para el tipo de recurso.
6. Escriba `mybucket123` para el ID de recurso.
7. Pulse **Asignar**.
8. Pulse **Sí** para confirmar que desea asignar la política de acceso público al recurso y pulse **Asignar**.
