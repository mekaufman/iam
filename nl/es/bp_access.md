---

copyright:

  years: 2018, 2019
lastupdated: "2019-01-28"

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:tip: .tip}

# Prácticas recomendadas para asignar acceso
{: #account_setup}

Para agilizar el proceso de asignación de accesos, puede aprovechar los grupos de acceso para asignar un número mínimo de políticas otorgándole el mismo acceso a todos los usuarios e ID de servicio que pertenecen al mismo grupo de acceso. Utilice estas prácticas recomendadas para obtener más información sobre cómo proporcionar a los usuarios acceso a recursos, grupos de recursos y servicios de gestión de cuentas.
{:shortdesc}

Para asegurarse de que su cuenta se ha configurado correctamente, consulte [Prácticas recomendadas para configurar su cuenta](/docs/account?topic=account-account_setup#account_setup) y [Prácticas recomendadas para organizar recursos en grupos de recursos](/docs/resources?topic=resources-bp_resourcegroups#bp_resourcegroups).
{: tip}

## ¿Cuál es una buena estrategia de grupo de acceso?
{: #rg_strategy}

Un grupo de acceso es una agrupación de ID de usuario e ID de servicio a los que se puede otorgar el mismo acceso de IAM. Puede asignar una única política al grupo en lugar de asignar el mismo acceso varias veces por usuario individual o ID de servicio.

Suponiendo que ha seguido las [prácticas recomendadas para configurar su cuenta](/docs/account?topic=account-account_setup#account_setup), una
forma lógica de asignar el acceso consiste en crear un grupo de acceso por nivel de acceso deseado. A continuación, puede correlacionar cada grupo de acceso con los grupos de recursos creados anteriormente. Por ejemplo, para controlar el acceso al proyecto `CustApp`, puede crear los siguientes grupos de acceso:

* Auditor-Group
* Developer-Group
* Admin-Group

Para Auditor-Group, asigne dos políticas de acceso que otorgaran acceso de visor a los grupos de recursos `CustApp-Test` y `CustApp-Prod`. Para Developer-Group, asigne dos políticas de acceso que otorgan acceso de editor a los entornos `CustApp-Dev` y `CustApp-Test`. Para Admin-Group, asigne tres políticas de acceso que otorguen acceso de administrador a los tres grupos de recursos `CustApp`.

Aunque estas sugerencias están diseñadas para un caso de ejemplo hipotético, puede configurar la correlación entre grupo de acceso y grupo de recursos que se ajuste a sus requisitos.

## Creación de grupos de acceso
{: #access-group-setup}

Para crear un grupo de acceso, complete los pasos siguientes: 

1. En la consola de {{site.data.keyword.Bluemix}}, pulse **Gestionar** &gt; **Acceso (IAM)** y seleccione **Grupos de acceso**.
2. Pulse **Crear**.
3. Escriba el nombre y la descripción para el grupo.
4. Pulse **Crear**.

Después de crear un grupo de acceso, puede añadir usuarios e ID de servicio al grupo.

## Cómo proporcionan acceso las políticas de acceso de IAM
{: #how_access}

Una política consta de un sujeto, un destino y un rol. En este caso, el sujeto es el grupo de acceso. El destino es aquello a lo que desea que acceda el sujeto, como por ejemplo un conjunto de recursos, una instancia de servicio, todos los servicios de la cuenta o todas las instancias de un servicio. El rol define el nivel de acceso que se otorga a un usuario.

Los roles utilizados con más frecuencia son visor, editor y administrador. El rol de visor proporciona la menor cantidad de acceso para ver instancias y grupos de recursos en una cuenta. El rol de editor tiene más acceso para crear, editar, suprimir y enlazar instancias de servicio. El rol de administrador incluye todo lo necesario para trabajar con una instancia de servicio y puede asignar acceso a los demás. Sin embargo, hay dos categorías distintas de roles que debe tener en cuenta: plataforma y servicio. Para obtener más información sobre los roles que se pueden asignar, consulte los [Roles de nube de IAM](/docs/iam?topic=iam-iamusermanrol#iamusermanrol). 

## Asignación de acceso a grupos de acceso
{: #assigning-access}

Puede organizar los recursos de un grupo de recursos y los usuarios y los ID de servicio de un grupo de acceso para facilitar lo máximo posible la asignación de acceso. Después de configurar cada uno, puede crear políticas de acceso para los grupos de acceso para asignar a los usuarios de la cuenta el acceso a los recursos que ha creado.

1. Pulse **Gestionar** &gt; **Acceso (IAM)** y seleccione **Grupos de acceso**.
2. Seleccione el nombre del grupo de acceso al que desea asignar acceso.
3. Seleccione el separador **Políticas de acceso** y, a continuación, pulse **Asignar acceso**. Tiene las siguientes opciones para asignar acceso:

  * **Asignar acceso a los recursos de un grupo de recursos**: utilice esta opción para asignar la política de dos partes que se necesita para los usuarios que crean recursos desde el catálogo y asignar los recursos a un grupo de recursos. Cuando utilice esta opción, puede otorgar acceso al propio grupo de recursos y a todos los recursos de un determinado grupo de recursos o a un solo servicio o instancia del grupo de recursos.
  * **Asignar acceso a recursos**: utilice esta opción para asignar acceso a todos los servicios habilitados para IAM de la cuenta o a un único servicio de la cuenta, pero no a un nivel de instancia.
  * **Asignar acceso a servicios de gestión de cuentas**: utilice esta opción para proporcionar un acceso de usuario a los servicios de gestión de cuentas como una forma de delegar algunas de sus funciones de propietario de la cuenta. Por ejemplo, puede delegar la capacidad de ver información de facturación y uso, de invitar y eliminar usuarios, de gestionar grupos de acceso, de gestionar servicios de catálogo o de gestionar ID de servicio. Puede proporcionar acceso a todos los servicios de gestión de cuentas o solo a uno.

Puede otorgar fácilmente acceso de administrador a varios usuarios sobre todo lo relacionado con la cuenta creando un grupo de acceso y asignándole dos políticas. Para crear la primera política, utilice la opción **Asignar acceso a recursos** y seleccione **Todos los servicios habilitados para Identity and Access** con el rol de administrador asignado. Para crear la segunda política, utilice la opción **Asignar acceso a servicios de gestión de cuentas** y seleccione **Todos los servicios de gestión de cuentas** con el rol de administrador asignado.
{: tip}


