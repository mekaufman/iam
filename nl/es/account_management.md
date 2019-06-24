---

copyright:

  years: 2019

lastupdated: "2019-06-03"

keywords: account management, access, access policy, account administrator

subcollection: iam

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:tip: .tip}
{:note: .note}

# Asignación de acceso a los servicios de gestión de cuentas
{: #account-services}

Como propietario de cuenta o administrador de un servicio de gestión de cuentas, puede utilizar los servicios de gestión de cuentas para otorgar acceso a los usuarios para invitar usuarios a la cuenta, realizar un seguimiento de la facturación y del uso y trabajar con casos de soporte. Los usuarios con acceso también pueden gestionar ID de servicio, acceder a políticas, catalogar entradas y acceder a grupos.

## Creación de políticas de acceso a los servicios de gestión de cuentas
{: #account-management-access}

Para asignar acceso a uno o a todos los servicios de gestión de cuentas, siga los pasos siguientes:

1. En la barra de menús, pulse **Gestionar** &gt; **Acceso (IAM)** y seleccione **Usuarios**.
2. En la fila correspondiente al usuario al que desea asignar acceso, seleccione el menú **Acciones** ![Icono Lista de acciones](../icons/action-menu-icon.svg) y pulse **Asignar acceso**.
3. Seleccione que desea asignar acceso a **Servicios de gestión de cuentas**.
4. Seleccione **Todos los servicios de gestión de cuentas** o seleccione un servicio de gestión de cuentas específico.
5. Seleccione cualquier combinación de roles para asignar el acceso deseado.

Para otorgar acceso completo a la cuenta a otro usuario con el fin de gestionar accesos de usuario y todos los recursos de la cuenta, debe asignar dos políticas. Una política que otorgue acceso al usuario a todos los recursos de la cuenta seleccionando **Todos los servicios habilitados de Identity and Access** con el rol de **Administrador** y **Gestor** asignado. Y una política que otorgue acceso al usuario a todos los recursos de gestión de cuentas de la cuenta seleccionando **Todos los servicios de gestión de cuentas** con el rol de **Administrador** asignado.
{: tip}

## Correlaciones de acciones y roles en los servicios de gestión de cuentas
{: #account-management-actions-roles}

En las tablas siguientes se indican las acciones que pueden realizar los usuarios cuando se les asigna un rol determinado para cada servicio de gestión de cuentas. Consulte la información para asegurarse de asignar el nivel de acceso correcto a los usuarios.

| Roles | Acciones |
|:-------|----------|
| Visor |   Ver miembros y grupos de acceso     |
| Operador | No aplicable    |
| Editor |  Ver, crear, editar y suprimir grupos <br><br> Añadir o eliminar usuarios de grupos     |
| Administrador |  Ver, crear, editar y suprimir grupos <br><br> Añadir o eliminar usuarios <br><br> Asignar acceso a un grupo <br><br> Gestionar el acceso para trabajar con grupos de acceso   |
{: caption="Tabla 1. Roles y acciones de ejemplo para el servicio de grupos de acceso" caption-side="top"}

| Roles | Acciones |
|:-------|----------|
| Visor |  Ver usuarios de la cuenta <br><br> Ver valores del perfil de usuario     |
| Operador | Ver usuarios de la cuenta <br><br> Ver valores del perfil de usuario  |
| Editor |  Ver, invitar, eliminar y actualizar usuarios de la cuenta <br><br> Ver y actualizar valores de perfil de usuario    |
| Administrador | Ver, invitar, eliminar y actualizar usuarios de la cuenta <br><br> Ver y actualizar valores de perfil de usuario    |
{: caption="Tabla 2. Roles y acciones de ejemplo para el servicio de gestión de usuarios" caption-side="top"}

| Roles | Acciones |
|:-------|----------|
| Visor |  Ver casos <br><br> Buscar casos      |
| Operador |  No aplicable    |
| Editor |  Ver casos <br><br> Buscar casos <br><br> Actualizar casos <br><br> Crear casos     |
| Administrador |  Ver casos <br><br> Buscar casos <br><br> Actualizar casos <br><br> Crear casos    |
{: caption="Tabla 3. Roles y acciones de ejemplo para el servicio del centro de soporte" caption-side="top"}

{: #billing-acct-mgmt}
| Roles | Acciones |
|:-------|----------|
| Visor | Ver valores de características de la cuenta <br><br> Ver suscripciones en la cuenta <br><br> Ver nombre de la cuenta <br><br> Ver grupos de recursos   |
| Operador | Ver valores de características de la cuenta <br><br> Ver suscripciones en la cuenta <br><br> Ver y cambiar nombre de la cuenta <br><br> Ver y actualizar grupos de recursos    |
| Editor |  Ver y actualizar los valores de características de la cuenta <br><br> Ver suscripciones en la cuenta <br><br> Ver ofertas en la cuenta <br><br> Ver y aplicar códigos de característica <br><br> Ver y cambiar nombre de la cuenta <br><br> Ver y actualizar límites de gasto <br><br> Ver, crear y actualizar grupos de recursos    |
| Administrador |  Ver y actualizar los valores de características de la cuenta <br><br> Ver suscripciones en la cuenta <br><br> Ver ofertas en la cuenta <br><br> Ver y aplicar códigos de característica <br><br> Ver y cambiar nombre de la cuenta <br><br> Ver y actualizar límites de gasto <br><br> Ver balances de suscripción y realizar un seguimiento del uso <br><br> Ver, crear, actualizar y asignar acceso para gestionar grupos de recursos  |
{: caption="Tabla 4. Roles y acciones de ejemplo para el servicio de facturación" caption-side="top"}

| Roles | Acciones |
|:-------|----------|
| Visor |   Ver ID     |
| Operador | Crear y suprimir ID y claves de API   |
| Editor |  Crear, actualizar y suprimir ID y claves de API  |
| Administrador |  Crear, actualizar y suprimir ID y claves de API <br><br> Asignar políticas de acceso a ID  |
{: caption="Tabla 5. Roles y acciones de ejemplo para el servicio de identidad IAM" caption-side="top"}
{: #identity-service-acct-mgmt}

Para el servicio IAM Identity Service, estas acciones se aplican a los ID de servicio dentro de la cuenta que el usuario no ha creado. Todos los usuarios pueden crear ID de servicio. Son los administradores de dichos ID y pueden crear la clave de API asociada y las políticas de acceso. Sin embargo, este servicio de gestión de cuentas se aplica a la capacidad de ver, suprimir y asignar acceso a los ID de servicio de la cuenta creada por otros usuarios.
{: note}

| Roles | Acciones |
|:-------|----------|
| Visor |   Ver servicios privados    |
| Operador | No aplicable    |
| Editor |   Cambiar los metadatos del objeto, pero no puede cambiar la visibilidad de los servicios privados     |
| Administrador |  Cambiar los metadatos de objeto o la visibilidad de los servicios privados y restringir la visibilidad de un servicio público   |
{: caption="Tabla 6. Roles y acciones de ejemplo para el servicio de catálogo global" caption-side="top"}

| Roles | Acciones |
|:-------|----------|
| Visor |  Todas las acciones del rol de visor para los servicios de gestión de cuentas     |
| Operador |  Todas las acciones del rol de operador para los servicios de gestión de cuentas     |
| Editor |  Todas las acciones del rol de editor para los servicios de gestión de cuentas y capacidad para crear grupos de recursos    |
| Administrador |  Todas las acciones del rol de administrador los servicios de gestión de cuentas y capacidad para crear grupos de recursos   |
{: caption="Tabla 7. Roles y acciones de ejemplo para una política sobre todos los servicios de acceso e identidad" caption-side="top"}
