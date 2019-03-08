---

copyright:

  years: 2018, 2019

lastupdated: "2019-01-30"

keywords: dynamic rules, access groups, specific identity attributes

subcollection: iam

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:tip: .tip}
{:note: .note}

# Creación de reglas dinámicas para grupos de acceso
{: #rules}

Puede crear reglas dinámicas para añadir de forma automática usuarios federados a grupos de acceso en función de determinados atributos de identidad. Cuando los usuarios inician una sesión con un ID federado, los datos del proveedor de identidades correlacionan dinámicamente los usuarios con un grupo de acceso en función de las reglas.
{:shortdesc}

Los usuarios ya tienen información de identidad específica dentro del dominio de la empresa, y cuando inician sesión con un ID federado, estos datos se pueden pasar mediante aserciones SAML. Las aserciones SAML o las sentencias de atributo configuradas dentro del proveedor de identidad proporcionan los datos que se utilizan para crear cada regla. Por ejemplo, puede haber una sentencia de atributo true o false que defina a los usuarios como un gestor. Esta información se puede utilizar para añadir todos los usuarios que son gestores a un grupo de acceso específico para los gestores que ha creado en la cuenta de {{site.data.keyword.Bluemix_notm}}. Para obtener más información, consulte la [Regla de ejemplo](/docs/iam?topic=iam-rules#example).

Únicamente los usuarios que ya están invitados a la cuenta se pueden correlacionar con grupos de acceso utilizando reglas dinámicas.
{: note}

## Configuración de reglas
{: #setup_rules}

Las reglas dinámicas se crean estableciendo condiciones que deben coincidir con los datos configurados dentro del proveedor de identidad y que se pasan con el ID federado de un usuario durante el inicio de sesión. Para crear una regla, siga estos pasos:

1. En la barra de menús, pulse **Gestionar** &gt; **Acceso (IAM)** y seleccione **Grupos de acceso**.
2. Seleccione el nombre del grupo de acceso para el que desea crear una regla para abrir la página de detalles de grupo.
3. Seleccione el separador **Reglas dinámicas**.
4. Pulse **Añadir regla**.
5. Especifique la información del proveedor de identidad. En la lista siguiente se proporcionan detalles para cada campo necesario.

<dl>
<dt>Nombre</dt>
<dd>Especifique un nombre personalizado para la regla que le ayude a recordar el tipo de usuarios que está añadiendo a un grupo de acceso.</dd>
<dt>Proveedor de identidad</dt>
<dd>Especifique el URI para el proveedor de identidad. Este es el campo "entityId" de SAML, a veces conocido como el ID de emisor, para el proveedor de identidad como parte de la configuración de federación para la incorporación con IBMid.</dd>
<dt>Caducidad (en horas)</dt>
<dd>Puede utilizar esta opción para proporcionar seguridad adicional estableciendo un límite de tiempo para el acceso asignado. Cada usuario debe iniciar sesión cada 24 horas para refrescar su acceso, pero puede establecer que el acceso caduque en menos de una hora. La pertenencia a grupos se revoca después de que caduque este periodo de tiempo.</dd>
<dt>Añadir usuarios cuando</dt>
<dd>El nombre de la sentencia de atributo debe especificarse en este campo. Este valor es específico del proveedor de identidad.</dd>
<dt>Comparador</dt>
<dd>Puede elegir entre Equals, Not Equals, Equals Ignore Case, Not Equals Ignore Case, In y Contains. Utilice la opción Contains cuando la sentencia de atributo tenga un tipo de matriz. Además, puede especificar más de un valor para que coincida utilizando la opción In.</dd>
<dt>Valor</dt>
<dd>Especifique el valor de atributo para la sentencia de atributo en la que se compara la regla.</dd>
</dl>

Puede añadir más de una condición para una regla. Todas las condiciones establecidas en la regla deben cumplirse para que un usuario se pueda añadir a un grupo de acceso.
{: tip}

## Regla de ejemplo
{: #example}

El ejemplo siguiente incluye valores para cada uno de los campos de la página **Añadir regla**. En esta regla, los usuarios que se identifican como gestores dentro del proveedor de identidad federado se correlacionan con un grupo de acceso de {{site.data.keyword.Bluemix_notm}} que tiene un conjunto de acceso específico solo para los gestores.

| Campo | Valor |
|----------|---------|
| Nombre | Regla de grupo de gestores |
| Proveedor de identidad | `https://idp.example.org/SAML2` |
| Caducidad (en horas) | 12 |
| Añadir usuarios cuando (nombre de atributo) | isManager |
| Comparador | Igual que  |
| Valor |  true |
{: caption="Tabla 1. Regla dinámica de ejemplo para grupos de acceso" caption-side="top"}
