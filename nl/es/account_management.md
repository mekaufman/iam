---

copyright:

  years: 2019

lastupdated: "2019-07-01"

keywords: account management, access, access policy, account administrator, user management, account management services, use account management services to grant users in the account access to invite users to the account, billing service, support center service, identity service, global catalog service, enterprise service

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

Como propietario de cuenta o administrador de un servicio de gestión de cuentas, puede utilizar estos servicios para otorgar a los usuarios acceso para que realicen tareas como invitar usuarios a la cuenta, realizar un seguimiento de la facturación y del uso y trabajar con casos de soporte. Los usuarios con políticas de acceso de gestión de cuenta
también pueden gestionar ID de servicio, acceder a políticas, catalogar entradas y acceder a grupos.
{:shortdesc}

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

## Acciones y roles para los servicios de gestión de cuentas
{: #account-management-actions-roles}

En las tablas siguientes se indican las acciones que pueden realizar los usuarios cuando se les asigna un rol determinado para cada servicio de gestión de cuentas. Consulte la información para asegurarse de asignar el nivel de acceso correcto a los usuarios. 

### Servicio de grupos de acceso de IAM
{: #access-groups-account-management}

Puede otorgar a los usuarios acceso para ver, crear, editar y suprimir grupos de acceso en la cuenta mediante el servicio de gestión de cuentas de grupos de acceso. 

| Roles | Acciones |
|:-------|----------|
| Visor |   Ver miembros y grupos de acceso     |
| Operador | No aplicable    |
| Editor |  Ver, crear, editar y suprimir grupos <br><br> Añadir o eliminar usuarios de grupos     |
| Administrador |  Ver, crear, editar y suprimir grupos <br><br> Añadir o eliminar usuarios <br><br> Asignar acceso a un grupo <br><br> Gestionar el acceso para trabajar con grupos de acceso   |
{: caption="Tabla 1. Roles y acciones de ejemplo para el servicio de grupos de acceso" caption-side="top"}

### Gestión de usuarios
{: #user-management-account-management}

Puede otorgar a los usuarios acceso para ver los usuarios de una cuenta, invitar y eliminar usuarios, y ver y actualizar valores de perfil de usuario con el servicio de gestión de cuentas de gestión de usuarios. 

| Roles | Acciones |
|:-------|----------|
| Visor |  Ver usuarios de la cuenta <br><br> Ver valores del perfil de usuario     |
| Operador | Ver usuarios de la cuenta <br><br> Ver valores del perfil de usuario  |
| Editor |  Ver, invitar, eliminar y actualizar usuarios de la cuenta <br><br> Ver y actualizar valores de perfil de usuario    |
| Administrador | Ver, invitar, eliminar y actualizar usuarios de la cuenta <br><br> Ver y actualizar valores de perfil de usuario    |
{: caption="Tabla 2. Roles y acciones de ejemplo para el servicio de gestión de usuarios" caption-side="top"}

El rol de visor en el servicio de gestión de usuarios es un rol que se suele asignar a los usuarios que también tienen asignado un rol para ver o gestionar casos de soporte. Esto se debe a que si un propietario de cuenta restringe la visibilidad de la lista de usuarios en los valores de IAM, puede hacer que los usuarios no puedan ver los casos de soporte abiertos por otros usuarios en la cuenta. Sin embargo, si se les asigna el rol de visor para el servicio de gestión de usuarios, el valor de visibilidad de la lista de usuarios no afecta a su capacidad para ver casos en la cuenta
{: tip}

### Centro de soporte
{: #support-center-account-management}

Puede otorgar a los usuarios acceso para gestionar casos de soporte mediante el servicio del centro de soporte.

| Roles | Acciones |
|:-------|----------|
| Visor |  Ver casos <br><br> Buscar casos      |
| Operador |  No aplicable    |
| Editor |  Ver casos <br><br> Buscar casos <br><br> Actualizar casos <br><br> Crear casos     |
| Administrador |  Ver casos <br><br> Buscar casos <br><br> Actualizar casos <br><br> Crear casos    |
{: caption="Tabla 3. Roles y acciones de ejemplo para el servicio del centro de soporte" caption-side="top"}

Resulta habitual asignar a los usuarios el rol de visor en el servicio de gestión de usuarios además de una política de acceso al centro de soporte para garantizar que los usuarios puedan ver todos los casos de la cuenta, independientemente del modo en que el propietario de la cuenta haya definido el valor de visibilidad de la lista. Si el valor de visibilidad de la lista de usuarios se establece en restringido, de modo que los usuarios tengan restringida la posibilidad de ver otros usuarios en la cuenta, puede quedar limitada la capacidad de un usuario para ver, buscar y gestionar casos de soporte en una cuenta que no ha abierto él mismo.
{: tip}

### Facturación
{: #billing-acct-mgmt}

Puede otorgar a los usuarios acceso para actualizar los valores de cuenta, ver suscripciones, ver ofertas, aplicar códigos de característica, actualizar los límites de gastos y realizar un seguimiento de la utilización mediante el servicio de facturación.

| Roles | Acciones |
|:-------|----------|
| Visor | Ver valores de características de la cuenta <br><br> Ver suscripciones en la cuenta <br><br> Ver nombre de la cuenta <br><br> Ver grupos de recursos   |
| Operador | Ver valores de características de la cuenta <br><br> Ver suscripciones en la cuenta <br><br> Ver y cambiar nombre de la cuenta <br><br> Ver y actualizar grupos de recursos    |
| Editor |  Ver y actualizar los valores de características de la cuenta <br><br> Ver suscripciones en la cuenta <br><br> Ver ofertas en la cuenta <br><br> Ver y aplicar códigos de característica <br><br> Ver y cambiar nombre de la cuenta <br><br> Ver y actualizar límites de gasto <br><br> Ver, crear y actualizar grupos de recursos    |
| Administrador |  Ver y actualizar los valores de características de la cuenta <br><br> Ver suscripciones en la cuenta <br><br> Ver ofertas en la cuenta <br><br> Ver y aplicar códigos de característica <br><br> Ver y cambiar nombre de la cuenta <br><br> Ver y actualizar límites de gasto <br><br> Ver balances de suscripción y realizar un seguimiento del uso <br><br> Ver, crear, actualizar y asignar acceso para gestionar grupos de recursos  |
{: caption="Tabla 4. Roles y acciones de ejemplo para el servicio de facturación" caption-side="top"}

### Servicio de identidad IAM
{: #identity-service-account-management}

Puede otorgar a los usuarios acceso para gestionar los ID de servicio mediante el servicio de identidad IAM. Para el servicio de identidad IAM, estas acciones se aplican a los ID de servicio dentro de la cuenta que el usuario no ha creado. Todos los usuarios pueden crear ID de servicio. Son los administradores de dichos ID y pueden crear la clave de API asociada y las políticas de acceso. Sin embargo, este servicio de gestión de cuentas se aplica a la capacidad de ver, suprimir y asignar acceso a los ID de servicio de la cuenta creada por otros usuarios.

| Roles | Acciones |
|:-------|----------|
| Visor |   Ver ID     |
| Operador | Crear y suprimir ID y claves de API   |
| Editor |  Crear, actualizar y suprimir ID y claves de API  |
| Administrador |  Crear, actualizar y suprimir ID y claves de API <br><br> Asignar políticas de acceso a ID  |
{: caption="Tabla 5. Roles y acciones de ejemplo para el servicio de identidad IAM" caption-side="top"}
{: #identity-service-acct-mgmt}


### Catálogo global
{: #global-catalog-account-management}

Puede otorgar a los usuarios acceso para ver los servicios privados en el catálogo o cambiar la visibilidad de otros usuarios para los servicios privados mediante el servicio de catálogo global.

| Roles | Acciones |
|:-------|----------|
| Visor |   Ver servicios privados    |
| Operador | No aplicable    |
| Editor |   Cambiar los metadatos del objeto, pero no puede cambiar la visibilidad de los servicios privados     |
| Administrador |  Cambiar los metadatos de objeto o la visibilidad de los servicios privados y restringir la visibilidad de un servicio público   |
{: caption="Tabla 6. Roles y acciones de ejemplo para el servicio de catálogo global" caption-side="top"}


### Opción Todos los servicios de gestión de cuentas
{: #all-account-management}

Para otorgar rápidamente a los usuarios un amplio conjunto de acceso de gestión de cuentas, puede asignar una política a la opción de todos los servicios de gestión de cuentas. En función del rol que se seleccione, el asunto de la política puede realizar todas las acciones aplicables por cada rol seleccionado para cada servicio de gestión de cuentas.


| Roles | Acciones |
|:-------|----------|
| Visor |  Todas las acciones del rol de visor para los servicios de gestión de cuentas     |
| Operador |  Todas las acciones del rol de operador para los servicios de gestión de cuentas     |
| Editor |  Todas las acciones del rol de editor para los servicios de gestión de cuentas y capacidad para crear grupos de recursos    |
| Administrador |  Todas las acciones del rol de administrador los servicios de gestión de cuentas y capacidad para crear grupos de recursos   |
{: caption="Tabla 7. Roles y acciones de ejemplo para una política sobre todos los servicios de acceso e identidad" caption-side="top"}


