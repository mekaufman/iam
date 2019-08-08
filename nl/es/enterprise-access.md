---

copyright:

  years: 2019

lastupdated: "2019-07-24"

keywords: enterprise access

subcollection: iam

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:tip: .tip}
{:note: .note}

# Gestión de usuarios para empresas
{: #enterprise-access}

Las empresas de {{site.data.keyword.cloud}} son útiles para grandes compañías u organizaciones que necesitan agrupar un conjunto de cuentas, manteniendo al mismo tiempo la separación y el aislamiento entre las cuentas de distintos departamentos o equipos. La gestión de los usuarios y su acceso a los recursos de cada cuenta siguen siendo completamente independientes, aunque las cuentas se añadan y se organicen dentro de en una empresa.
{:shortdesc}

Consulte [¿Qué es una empresa?](/docs/account?topic=account-enterprise) para obtener más información sobre las empresas.

La lista de usuarios de cada cuenta secundaria de una empresa sólo es accesible para los usuarios de dicha cuenta secundaria. Esto significa que los usuarios invitados a la empresa y los usuarios invitados a las cuentas dentro de la empresa siguen siendo completamente independientes. La ventaja de esto es que puede añadir varias cuentas a una empresa y organizarlas según sea necesario en grupos de cuentas, pero mantener las listas de usuarios inaccesibles para las otras cuentas.

En la mayoría de los casos, deseará añadir a su cuenta de empresa sólo los usuarios que necesiten la capacidad de gestionar la empresa. Según el rol que el usuario tenga asignado en el [servicio de gestión de cuentas de empresa](/docs/iam?topic=iam-assign-access-enterprise), puede tener distintos niveles de acceso para gestionar la empresa. Por ejemplo, un usuario al que se ha asignado al rol de Administrador en el servicio de Empresa puede cambiar el nombre de la empresa, actualizar el dominio, ver el uso, crear cuentas y otras cosas. Sin embargo, un usuario con el rol de visor o de operador sólo puede ver la jerarquía de cuentas y grupos de cuentas de la empresa.

Invitar a usuarios a la cuenta de empresa no proporciona acceso para gestionar ninguna de las cuentas secundarias dentro de la empresa ni sus recursos. Si añade un usuario a una cuenta de empresa que contiene varias cuentas, estos usuarios no tienen automáticamente acceso para gestionar esas cuentas en lo que respecta a la gestión de usuarios, la facturación y otros. Los usuarios de una cuenta de empresa tampoco tienen acceso a ningún recurso de otras cuentas de la empresa.

Si desea que un usuario gestione la empresa y tenga acceso a recursos dentro de cuentas secundarias, debe invitarlo a las dos cuentas. Asignar políticas de acceso en la cuenta de empresa permite al usuario gestionar la empresa. Y asignar políticas de acceso dentro de la cuenta secundaria permite al usuario gestionar recursos específicos o completar tareas de gestión de cuentas sólo dentro de esa cuenta.
{: note}

Para obtener información sobre cómo asignar acceso a los usuarios en una empresa, consulte [Asignación de acceso de empresa](/docs/iam?topic=iam-assign-access-enterprise).
